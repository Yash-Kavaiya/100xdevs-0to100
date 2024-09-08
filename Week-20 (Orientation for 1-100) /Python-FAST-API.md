# FAST API 
Certainly! I'll create a FastAPI backend with the specified routes and functionality. We'll use sample responses to simulate the behavior of a Gemini-like LLM. Here's the full FastAPI backend implementation:



```python
from fastapi import FastAPI, Query
from pydantic import BaseModel
from typing import Optional

app = FastAPI()

class PromptRequest(BaseModel):
    prompt: str

def generate_llm_response(prompt: str, is_private: bool) -> str:
    # Simulating LLM response generation
    if is_private:
        return f"Private response for: {prompt}"
    else:
        return f"Public response for: {prompt}"

@app.post("/developer")
async def developer_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Developer", "response": response}

@app.post("/tester")
async def tester_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tester", "response": response}

@app.post("/pm")
async def pm_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Project Manager", "response": response}

@app.post("/techlead")
async def techlead_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tech Lead", "response": response}

@app.post("/insights")
async def insights_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Insights", "response": response}

@app.post("/search")
async def search_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Search", "response": response}

@app.post("/db")
async def db_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Database", "response": response}

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=8000)

```

This FastAPI backend implements the requested routes: /developer, /tester, /pm, /techlead, /insights, /search, and /db. Each route accepts a POST request with a JSON body containing a "prompt" field and an optional query parameter "private-data" (default is False).

Here's a breakdown of the implementation:

1. We import necessary modules from FastAPI and define a Pydantic model for the request body.

2. The `generate_llm_response` function simulates an LLM response based on the prompt and privacy setting.

3. Each route is implemented as a separate function with the `@app.post()` decorator.

4. The routes accept a `PromptRequest` object and an optional `private_data` query parameter.

5. The response includes the role and the generated LLM-like response.

6. We've included a `__main__` block to run the server using uvicorn.

To run this backend:

1. Save the code in a file, e.g., `main.py`
2. Install the required packages: `pip install fastapi uvicorn`
3. Run the server: `python main.py`

The server will start on `http://0.0.0.0:8000`.

To test the API, you can use tools like curl or Postman. Here's an example curl command:

```
curl -X POST "http://localhost:8000/developer?private_data=true" -H "Content-Type: application/json" -d '{"prompt": "Explain dependency injection"}'
```

This will return a response like:

```json
{
  "role": "Developer",
  "response": "Private response for: Explain dependency injection"
}
```

The implementation simulates LLM-like responses without actually using a real LLM. To integrate with a real LLM like Google's Gemini, you would need to replace the `generate_llm_response` function with actual API calls to the LLM service.

Certainly! I'll add some GET requests to test the web functionality of our FastAPI backend. These GET requests will provide a simple way to check if the server is running and to retrieve some basic information.



```python
from fastapi import FastAPI, Query
from pydantic import BaseModel
from typing import Optional

app = FastAPI()

class PromptRequest(BaseModel):
    prompt: str

def generate_llm_response(prompt: str, is_private: bool) -> str:
    # Simulating LLM response generation
    if is_private:
        return f"Private response for: {prompt}"
    else:
        return f"Public response for: {prompt}"

# New GET routes for testing
@app.get("/")
async def root():
    return {"message": "Welcome to the FastAPI LLM-like backend!"}

@app.get("/health")
async def health_check():
    return {"status": "healthy"}

@app.get("/info")
async def info():
    return {
        "app_name": "FastAPI LLM-like Backend",
        "version": "1.0.0",
        "available_routes": [
            "/developer", "/tester", "/pm", "/techlead",
            "/insights", "/search", "/db"
        ]
    }

# Existing POST routes
@app.post("/developer")
async def developer_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Developer", "response": response}

@app.post("/tester")
async def tester_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tester", "response": response}

@app.post("/pm")
async def pm_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Project Manager", "response": response}

@app.post("/techlead")
async def techlead_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tech Lead", "response": response}

@app.post("/insights")
async def insights_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Insights", "response": response}

@app.post("/search")
async def search_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Search", "response": response}

@app.post("/db")
async def db_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Database", "response": response}

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=8000)

```

I've added three new GET routes to the FastAPI backend:

1. `/` (root): A welcome message for the API.
2. `/health`: A simple health check endpoint.
3. `/info`: Provides basic information about the API, including available routes.

These new routes will allow you to easily test if the web server is running and responding correctly. Here's how you can use these new routes:

1. Root route:
   ```
   curl http://localhost:8000/
   ```
   Expected response:
   ```json
   {"message": "Welcome to the FastAPI LLM-like backend!"}
   ```

2. Health check:
   ```
   curl http://localhost:8000/health
   ```
   Expected response:
   ```json
   {"status": "healthy"}
   ```

3. API info:
   ```
   curl http://localhost:8000/info
   ```
   Expected response:
   ```json
   {
     "app_name": "FastAPI LLM-like Backend",
     "version": "1.0.0",
     "available_routes": [
       "/developer", "/tester", "/pm", "/techlead",
       "/insights", "/search", "/db"
     ]
   }
   ```

These GET routes provide a quick way to verify that your API is up and running, and they give some basic information about the available endpoints.

To test the API, you can still use the same method as before for the POST routes. For example:

```
curl -X POST "http://localhost:8000/developer?private_data=true" -H "Content-Type: application/json" -d '{"prompt": "Explain dependency injection"}'
```




```
from fastapi import FastAPI, Query
from pydantic import BaseModel
from typing import Optional

app = FastAPI()

class PromptRequest(BaseModel):
    prompt: str

def generate_llm_response(prompt: str, is_private: bool) -> str:
    # Simulating LLM response generation
    if is_private:
        return f"Private response for: {prompt}"
    else:
        return f"Public response for: {prompt}"

# New GET routes for testing
@app.get("/")
async def root():
    return {"message": "Welcome to the FastAPI LLM-like backend!"}

@app.get("/health")
async def health_check():
    return {"status": "healthy"}

@app.get("/info")
async def info():
    return {
        "app_name": "FastAPI LLM-like Backend",
        "version": "1.0.0",
        "available_routes": [
            "/developer", "/tester", "/pm", "/techlead",
            "/insights", "/search", "/db"
        ]
    }

# Existing POST routes
@app.post("/developer")
async def developer_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Developer", "response": response}

@app.post("/tester")
async def tester_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tester", "response": response}

@app.post("/pm")
async def pm_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Project Manager", "response": response}

@app.post("/techlead")
async def techlead_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Tech Lead", "response": response}

@app.post("/insights")
async def insights_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Insights", "response": response}

@app.post("/search")
async def search_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Search", "response": response}

@app.post("/db")
async def db_route(request: PromptRequest, private_data: Optional[bool] = Query(False)):
    response = generate_llm_response(request.prompt, private_data)
    return {"role": "Database", "response": response}

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=8000)
```
