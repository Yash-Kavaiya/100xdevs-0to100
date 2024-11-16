# 14.2 | NextJS Backend

**Introduction**

Next.js is a popular React framework that extends the capabilities of React by providing server-side rendering (SSR) and static site generation (SSG) out of the box. However, beyond just rendering frontend components, Next.js is considered a full-stack framework because it allows developers to write both frontend and backend code within the same project. This unified approach simplifies development workflows and offers several advantages, such as a single codebase, no Cross-Origin Resource Sharing (CORS) issues, and ease of deployment.

![](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F085e8ad8-528e-47d7-8922-a23dc4016453%2F293901d8-52c1-468b-8da4-118a492cc4d5%2FScreenshot_2024-03-03_at_1.19.40_PM.png?table=block&id=3cc70195-060b-4a7c-a4fb-a4f5788cc473&cache=v2)

**Handling Frontend and Backend Code in the Same Process**

1. **Server-Side Rendering (SSR):**

   Next.js enables server-side rendering of React components. When a request is made to a Next.js application, the server renders the React components into HTML and sends them to the client. This process happens on the server side before the HTML is delivered to the browser, improving performance and SEO.

2. **API Routes:**

   Next.js allows you to create API endpoints directly within your application using **API Routes**. These are built-in backend routes that can handle HTTP requests and are defined within the `pages/api` directory. For example:

   ```javascript
   // pages/api/hello.js
   export default function handler(req, res) {
     res.status(200).json({ message: 'Hello World' });
   }
   ```

   This endpoint can be accessed at `/api/hello`, and you can use it to interact with databases, authenticate users, or handle any server-side logic.

3. **Middleware:**

   Next.js also supports middleware functions that run before requests are processed. Middleware can be used for tasks like authentication checks, logging, and modifying requests or responses.

---

**Advantages of Next.js as a Full-Stack Framework**

1. **Single Codebase for All Your Codebase:**

   - **Unified Development Environment:**
     - Having both frontend and backend code in the same project simplifies development. Developers can easily navigate between frontend components and backend logic without switching repositories or projects.
   - **Code Sharing:**
     - You can share code between the frontend and backend, such as utility functions, types, and constants. This reduces code duplication and keeps your code DRY (Don't Repeat Yourself).
   - **Consistent Technologies:**
     - Since both frontend and backend are written in JavaScript (or TypeScript), there's no need to switch languages or contexts, which can increase productivity and reduce the learning curve for new team members.

2. **No CORS Issues, Single Domain Name for Your Frontend and Backend:**

   - **Simplified Networking:**
     - CORS issues occur when the frontend and backend are on different domains or ports, and the browser's same-origin policy blocks the requests. With Next.js, your API routes and frontend are served from the same domain, eliminating CORS-related problems.
   - **Secure and Efficient Communication:**
     - Since requests don't have to cross domain boundaries, you can avoid unnecessary preflight requests and potential security vulnerabilities associated with CORS misconfigurations.
   - **Cookie and Authentication Handling:**
     - Managing authentication tokens or sessions is simpler because cookies are shared across the same domain. You don't have to deal with complex setups to share authentication states between different domains.

3. **Ease of Deployment, Deploy a Single Codebase:**

   - **Simplified CI/CD Pipelines:**
     - Deploying a single application means you have one build and deployment process. This reduces complexity in your continuous integration and continuous deployment pipelines.
   - **Cost-Effective Hosting:**
     - Many hosting providers, like Vercel (the company behind Next.js), offer optimized platforms for Next.js applications. You can deploy both your frontend and backend together without needing separate hosting services.
   - **Scalability:**
     - Next.js applications can be easily scaled horizontally. Since the frontend and backend are part of the same application, scaling the application scales both parts simultaneously.
   - **Environment Management:**
     - Managing environment variables and configurations is more straightforward when dealing with a single application. You can define your variables in one place and access them from both frontend and backend code.

---

**Additional Benefits**

- **Optimized Performance:**
  - Next.js optimizes both frontend and backend performance. Features like automatic code splitting, image optimization, and server-side rendering contribute to faster load times and better user experiences.

- **Built-in Routing:**
  - Next.js provides a powerful routing system for both pages and API routes. This reduces the need for external libraries and keeps your routing logic consistent.

- **Community and Ecosystem:**
  - Being a widely adopted framework, Next.js has a strong community and ecosystem. There are numerous plugins, tutorials, and resources available to help you build robust applications.

- **Developer Experience:**
  - Features like hot module replacement, TypeScript support, and comprehensive error handling enhance the developer experience, making it enjoyable to build applications with Next.js.

**Conclusion**

Next.js stands out as a full-stack framework by seamlessly integrating frontend and backend development within a single codebase. This approach brings multiple advantages, including eliminating CORS issues, simplifying deployment, and enhancing developer productivity. By handling both the client and server-side code in the same process, Next.js allows developers to build efficient, scalable, and maintainable web applications with ease.

Certainly! Below is a table that compares data fetching in React and Next.js, highlighting the key differences and functionalities between the two.

---

**Comparison of Data Fetching in React vs. Next.js**

| Aspect                           | **React**                                                  | **Next.js**                                                |
|----------------------------------|------------------------------------------------------------|------------------------------------------------------------|
| **Rendering Type**               | Client-Side Rendering (CSR)                                | Supports CSR, Server-Side Rendering (SSR), Static Site Generation (SSG), and Incremental Static Regeneration (ISR) |
| **Data Fetching Methods**        | - `useEffect` hook<br>- Class component lifecycle methods  | - `getStaticProps`<br>- `getServerSideProps`<br>- `getStaticPaths`<br>- API Routes<br>- `useEffect` for CSR |
| **When Data is Fetched**         | After component mounts on the client side                  | Before rendering on the server side or at build time       |
| **SEO Friendliness**             | Less SEO-friendly due to initial empty HTML                | More SEO-friendly; pre-renders pages with data             |
| **Initial Load Performance**     | May have slower initial load due to client-side data fetching | Faster initial load with SSR and SSG as data is pre-fetched |
| **Complexity**                   | Simpler setup for client-only applications                 | More complex but offers powerful data fetching strategies  |
| **Server-Side Data Fetching**    | Not supported out of the box                               | Built-in support with server-side data fetching methods    |
| **Static Site Generation**       | Requires additional tools (e.g., Gatsby)                   | Built-in SSG with `getStaticProps`                         |
| **Incremental Static Regeneration (ISR)** | Not available                                           | Supported; allows updating static content after deployment |
| **Routing**                      | Requires React Router or similar libraries                 | File-system based routing; dynamic routes supported        |
| **API Routes**                   | Requires separate backend setup or external APIs           | Built-in API Routes within the application                 |
| **Code Splitting**               | Manual setup with `React.lazy` and `Suspense`              | Automatic code splitting for each page                     |
| **Access to Request Context**    | Not available during rendering                             | Available in server-side data fetching methods             |
| **Environment Variables**        | Exposed to the client unless configured otherwise          | Securely used in server-side code without exposing to client |
| **Authentication Handling**      | Client-side authentication or requires custom server setup | Server-side authentication during data fetching            |
| **Third-Party Libraries**        | May need Redux, SWR, or React Query for state management   | Can use same libraries; Next.js also provides data fetching mechanisms |
| **Data Caching**                 | Client-side caching with libraries                         | Built-in caching with SSG and ISR                          |
| **Error Handling**               | Handled within components or with error boundaries         | Can handle errors in data fetching methods                 |
| **Streaming and Suspense Support** | Experimental support                                       | Supports React Suspense and streaming SSR                  |

---

### **Detailed Comparison**

#### 1. **Rendering Type**

- **React:**
  - Primarily uses **Client-Side Rendering (CSR)**.
  - The initial HTML is minimal; JavaScript loads and renders the content on the client.
- **Next.js:**
  - Supports **CSR**, **Server-Side Rendering (SSR)**, **Static Site Generation (SSG)**, and **Incremental Static Regeneration (ISR)**.
  - Pre-renders pages on the server or at build time, providing fully rendered HTML to the client.

#### 2. **Data Fetching Methods**

- **React:**
  - Data is fetched using the `useEffect` hook in functional components.
  - In class components, data fetching is done in lifecycle methods like `componentDidMount`.
- **Next.js:**
  - Provides special asynchronous functions:
    - `getStaticProps` for SSG.
    - `getServerSideProps` for SSR.
    - `getStaticPaths` for dynamic routes in SSG.
  - Can still use `useEffect` for client-side data fetching.

#### 3. **When Data is Fetched**

- **React:**
  - Data is fetched **after** the component mounts on the client.
  - Can cause a delay in content display and affect SEO.
- **Next.js:**
  - Data can be fetched **before** rendering the page on the server or at build time.
  - Results in faster page loads and better SEO.

#### 4. **SEO Friendliness**

- **React:**
  - Initial page load may be empty or have loading indicators.
  - Search engines may not index content rendered client-side effectively.
- **Next.js:**
  - Since pages are pre-rendered with content, they are more SEO-friendly.
  - Improves visibility on search engines.

#### 5. **Initial Load Performance**

- **React:**
  - May experience slower initial load times due to fetching data after rendering.
- **Next.js:**
  - Faster initial load times as data is available when the page is served.
  - Reduces the time to first meaningful paint.

#### 6. **Complexity**

- **React:**
  - Simpler for projects that don't require server-side rendering or SEO optimization.
- **Next.js:**
  - Slightly more complex due to additional features.
  - Provides powerful tools for data fetching and rendering strategies.

#### 7. **Server-Side Data Fetching**

- **React:**
  - Does not support server-side data fetching out of the box.
  - Requires setting up a separate server or using external APIs.
- **Next.js:**
  - Built-in support with `getServerSideProps`.
  - Fetch data on each request on the server side.

#### 8. **Static Site Generation**

- **React:**
  - Needs additional frameworks like Gatsby for SSG.
- **Next.js:**
  - Built-in SSG capabilities with `getStaticProps`.
  - Generates static HTML at build time.

#### 9. **Incremental Static Regeneration (ISR)**

- **React:**
  - Not available.
- **Next.js:**
  - Allows updating static pages after deployment.
  - Can revalidate pages at runtime.

#### 10. **Routing**

- **React:**
  - Requires libraries like React Router for client-side routing.
- **Next.js:**
  - File-system based routing.
  - Supports dynamic routes and nested routes.

#### 11. **API Routes**

- **React:**
  - Needs a separate backend or relies on external APIs.
- **Next.js:**
  - Can create API endpoints within the application.
  - Defined in the `/pages/api` directory.

#### 12. **Code Splitting**

- **React:**
  - Manual code splitting with `React.lazy` and `Suspense`.
- **Next.js:**
  - Automatic code splitting.
  - Each page only loads what's necessary.

#### 13. **Access to Request Context**

- **React:**
  - No access to HTTP request or response objects during rendering.
- **Next.js:**
  - `getServerSideProps` and API routes have access to request and response.
  - Useful for authentication and personalized content.

#### 14. **Environment Variables**

- **React:**
  - Environment variables need to be prefixed with `REACT_APP_` and are exposed to the client.
- **Next.js:**
  - Supports server-side environment variables.
  - Can keep sensitive data secure.

#### 15. **Authentication Handling**

- **React:**
  - Typically handled on the client side.
  - Requires additional setup for secure authentication.
- **Next.js:**
  - Can handle authentication on the server side.
  - Provides more secure and seamless user experiences.

#### 16. **Third-Party Libraries**

- **React:**
  - May need libraries for state management and data fetching (e.g., Redux, SWR).
- **Next.js:**
  - Can use the same libraries.
  - Offers built-in data fetching methods that reduce the need for extra libraries.

#### 17. **Data Caching**

- **React:**
  - Client-side caching managed by the developer or third-party libraries.
- **Next.js:**
  - Can cache data at build time with SSG.
  - ISR allows for caching with revalidation.

#### 18. **Error Handling**

- **React:**
  - Error boundaries for component errors.
  - Needs manual error handling for data fetching.
- **Next.js:**
  - Can handle errors in `getServerSideProps` and `getStaticProps`.
  - Custom error pages and error handling mechanisms.

#### 19. **Streaming and Suspense Support**

- **React:**
  - Experimental support for Suspense with data fetching.
- **Next.js:**
  - Supports React Suspense and streaming for SSR.
  - Enables incremental rendering of parts of the UI.


### **Conclusion**

- **React** is ideal for applications that primarily need client-side rendering and where SEO is not a primary concern.
- **Next.js** extends React's capabilities by providing built-in solutions for server-side rendering, static site generation, and flexible data fetching strategies.
- Choosing between React and Next.js depends on the specific needs of your project, such as SEO requirements, performance considerations, and development complexity.

**Where Is the Loader? Do We Even Need a Loader?**

In your current implementation, **there is no loader displayed on the client side**, and in this specific case, **you do not need one**. Here's why:

1. **Server-Side Data Fetching**:

   - You're using an `async` component in Next.js to fetch data on the **server side** before the page is rendered.
   - The function `getUserDetails()` is called during the server-side rendering process.
   - As a result, the user receives a fully rendered HTML page with the user details already populated.

2. **No Client-Side Loading State**:

   - Since the data fetching happens **before** the page is sent to the client, there is no period where the client is waiting for data to load.
   - The usual need for a loader arises when data fetching occurs **after** the page has loaded on the client side (e.g., using `useEffect` in React).

3. **User Experience**:

   - From the user's perspective, the page loads instantly with all the data displayed.
   - There is no blank state or placeholder content that would necessitate a loading indicator.

**Why You Don't Need a Loader in This Scenario**

- **Immediate Data Availability**:
  - The data is available at the time of rendering, so there is no delay that the user would perceive.
- **Optimized Performance**:
  - By avoiding unnecessary client-side data fetching, you reduce the amount of JavaScript executed on the client, leading to faster load times.
- **Simplified Code**:
  - Not having to manage loading states or display loaders simplifies your component logic.

**When Would You Need a Loader?**

You would need a loader if:

- **Client-Side Data Fetching**:
  - If you were fetching data on the client side using hooks like `useEffect`, there would be a period where the data is not yet available, and you might want to display a loader.
- **Asynchronous User Interactions**:
  - If the user triggers additional data fetching after the initial page load (e.g., clicking a button to load more content), you might need a loader to indicate that data is being loaded.

**Example of When a Loader Is Needed**

If you modify your component to fetch data on the client side:

```jsx
"use client"; // Next.js directive for client-side components
import { useEffect, useState } from "react";
import axios from "axios";

export default function Home() {
  const [userData, setUserData] = useState(null);

  useEffect(() => {
    async function getUserDetails() {
      const response = await axios.get("https://api.example.com/user/details");
      setUserData(response.data);
    }
    getUserDetails();
  }, []);

  if (!userData) {
    return <div>Loading...</div>; // Loader displayed while data is fetched
  }

  return (
    <div>
      <div>Name: {userData.name}</div>
      <div>Email: {userData.email}</div>
    </div>
  );
}
```

In this example:

- The component renders on the client.
- There's an initial state where `userData` is `null`.
- A loader (`Loading...`) is displayed until the data is fetched.
- This approach can lead to a flash of empty content and isn't ideal for SEO.

**Advantages of Your Current Server-Side Approach**

- **Improved SEO**:
  - Search engines can index the fully rendered content.
- **Better Performance**:
  - Users receive the complete page without additional client-side data fetching delays.
- **No Need for Loaders**:
  - Simplifies your UI components by removing the need to handle loading states.

**Conclusion**

In your current Next.js application:

- **The loader is not present because it's unnecessary**.
- **You don't need a loader** since the data is fetched during server-side rendering.
- The user benefits from a seamless experience with immediate access to the content.

---

**Key Takeaways**:

- **Server-side rendering in Next.js eliminates the need for client-side loaders** for initial data fetching.
- **Loaders are primarily used when data fetching happens on the client side**, and there's a delay before data becomes available.
- **By fetching data on the server**, you provide a faster and more SEO-friendly experience.

**Additional Notes**:

- If you plan to implement features that require client-side data fetching or interactions that fetch data after the initial render, you may need to incorporate loaders at that point.
- Always consider the user experience and choose the data fetching strategy that best fits the needs of your application.

 