## **Serverless Functions**

### What are backends servers?

You might’ve used express to create a Backend server. The way to run it usually is node index.js which starts a process on a certain port (3000 for example)


### **What it is:**  
Serverless functions (also known as Functions-as-a-Service or FaaS) offer a way to deploy your backend code without having to manage the underlying infrastructure (like VMs). You simply provide the code, and the service provider handles the rest.

Absolutely! Here's a breakdown of serverless backends tailored to the easier definition you've provided:

**What are Serverless Backends?**

In a nutshell, serverless backends let you focus solely on writing your Express routes (or comparable functions in other frameworks) without managing traditional server infrastructure. Think of it like this:

* **You:**  Provide the application logic – define the routes and the code that handles requests.
* **Serverless Platform:** Does the heavy lifting of:
    * **Deployment:** Handles packaging and deploying your code.
    * **Autoscaling:**  Automatically scales resources up or down to match the number of incoming requests.
    * **Billing:** Charges you based on the number of requests your backend handles and the resources it consumes. You don't pay for idle time.

**Example Providers:**

* **AWS Lambda + API Gateway:** A popular combination for creating serverless REST APIs.
* **Netlify Functions:** Super developer-friendly, integrated with Netlify's deployment platform.
* **Cloudflare Workers:** Leverages Cloudflare's edge network for potential performance boosts.
* **Vercel Serverless Functions:**  Great if your project already lives within the Vercel ecosystem

**Pros**

* **Effortless Development:** No more fussing around with servers or scaling configurations.
* **True Pay-per-use Pricing:**  Ideal for applications with fluctuating traffic or smaller projects with sensitive budgets. 
* **Rapid Iteration:**  Go from code changes to deployment in minutes.

**Cons**

* **Cost at Scale:** If you have a consistently high request volume, serverless might become more expensive than managing your own VMs long-term.
* **Cold Starts:**  The first invocation of a function might be slower since it needs to set up a container. This can impact latency-sensitive parts of your application.
* **Vendor Lock-In:** Switching serverless platforms can be tricky  since they often rely on provider-specific tools.

**Is It the Right Choice?**

Serverless backends shine in these scenarios:

* **Prototyping and MVPs:** Get your product out the door fast, focus on development, and only worry about scaling when you need to.
* **Applications with Spiky Traffic:** Handle sudden bursts of requests effortlessly without overpaying during downtime.
* **Smaller Projects:** Minimize overhead costs, which is essential for smaller apps or side projects.

Let me know if you'd like a deeper dive into a specific serverless framework or how to migrate an existing Express application to a serverless backend! 

You're absolutely right! Here's why serverless architecture shines in those scenarios, with some additional insights:

**When you have to get off the ground fast and don't want to worry about deployments**

* **Minimized DevOps:** Serverless eliminates much of the traditional server setup. You focus on code, not infrastructure provisioning.
* **Quick Iterations:**  Deploy changes in a simplified manner, accelerating your development cycle. Ideal for rapid prototyping and MVP (Minimum Viable Product) creation. 

**When you can't anticipate the traffic and don't want to worry about autoscaling**

* **Traffic Spikes? No Problem:** Serverless handles unexpected bursts without pre-configuring complex scaling setups.
* **Downtime is Costly:** For applications where sudden popularity surges are possible (e.g., viral content), serverless prevents downtime due to overload.

**If you have very low traffic and want to optimize for costs**

* **Pay ONLY for What You Use:** No idle servers = no money wasted when there are few or no requests coming in.
* **Budget-Friendly for Small Projects:** Excellent for side projects, hobbies, or applications with minimal initial usage.

**Additional Considerations**

* **Event-Driven Workloads:** Serverless functions are well-suited to event-based processing (e.g., image resizing after upload, data processing, etc.).
* **Microservice Architectures:** A good option for breaking down larger applications into smaller, independently deployable serverless functions.

Summary of the blog post [How Cloudflare Workers Work?](https://developers.cloudflare.com/workers/reference/how-workers-works/):

**Cloudflare Workers** are serverless functions that run on Cloudflare's global network of data centers. They are similar to JavaScript code written for the browser or Node.js, but there are a few key differences:

* **Isolated Environments:** Cloudflare Workers are executed in isolated environments called isolates. Isolates are lightweight and start up very quickly, which helps to improve performance. Each isolate has its own memory space, so code running in one isolate cannot affect code running in another isolate. This helps to improve security and stability.
* **Execution Flow:** When a request is made to a Worker, it is routed to the nearest data center and then to an available isolate. The isolate then executes the `fetch()` handler, which is a function that defines how the Worker should respond to the request. The `fetch()` handler can return a Response object, which contains the data that will be sent back to the client. Once the `fetch()` handler has finished executing, the isolate may be evicted from memory, especially if resources are scarce. However, this will not happen until all of the isolate's events have been properly resolved.

**In summary,** Cloudflare Workers are a type of serverless function that is designed to be fast, secure, and scalable. They are executed in isolated environments and can be used to respond to a variety of HTTP requests.

**Key differences from Node.js:**

* **Custom Runtime:** Cloudflare Workers don't use the Node.js runtime. Instead, they have a custom runtime environment called "V8" that is based on the V8 JavaScript engine used in Chrome and Node.js.
* **Limited Functionality:** While similar to Node.js and browser JavaScript, Cloudflare Workers have some limitations due to their serverless nature. For example, they cannot access the DOM or the file system.


| Feature | Isolates | Containers |
|---|---|---|
| **Runtime** | Shared JavaScript runtime | Individual instances of a language runtime |
| **Overhead** | Lower overhead | Higher overhead |
| **Security** | Secure sandbox environment | Less secure |
| **Start up time** | Faster start up time | Slower start up time due to cold starts |
| **Lifespan** | Not long-lived, can be evicted | Longer lifespan |

### Initializing a worker
To create and deploy your application, you can take the following steps - 
-Initialize a worker
```
npm create cloudflare -- my-app
```

Select no for Do you want to deploy your application
 
- Explore package.json dependencies
```
"wrangler": "^3.0.0"
```

Notice express is not a dependency there
- tart the worker locally

```
npm run dev
```
How to return json?
```
export default {
	async fetch(request: Request, env: Env, ctx: ExecutionContext): Promise<Response> {
		return Response.json({
			message: "hi"
		});
	},
};
```

Question - Where is the express code? HTTP Server?
Cloudflare expects you to just write the logic to handle a request. 
Creating an HTTP server on top is handled by cloudflare
Question - How can I do routing ? 
In express, routing is done as follows - 
```
import express from "express"
const app = express();
app.get("/route", (req, res) => {
	// handles a get request to /route
});
```
How can you do the same in the Cloudflare environment?
```
export default {
	async fetch(request: Request, env: Env, ctx: ExecutionContext): Promise<Response> {
		console.log(request.body);
		console.log(request.headers);
		
		if (request.method === "GET") {
			return Response.json({
				message: "you sent a get request"
			});
		} else {
			return Response.json({
				message: "you did not send a get request"
			});
		}
	},
};
 ```
💡How to get query params - https://community.cloudflare.com/t/parse-url-query-strings-with-cloudflare-workers/90286
 
Cloudflare does not expect a routing library/http server out of the box. You can write a full application with just the constructs available above.
 
We will eventually see how you can use other HTTP frameworks (like express) in cloudflare workers.
 