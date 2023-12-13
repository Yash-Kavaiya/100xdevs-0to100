

#### What is ECMAScript ?
- ECMAScript is a standardized scripting language specification. JavaScript is an implementation of the ECMAScript specification and is used predominantly for web development. It's a versatile language that allows developers to create interactive elements within web pages.

Docs:- https://tc39.es/ecma262/#sec-numbers-and-dates
#### What is Javascript?

JavaScript is a high-level, versatile programming language primarily used for web development. It's an essential component for creating dynamic and interactive content on websites. JavaScript allows developers to add functionalities like interactivity, animations, and complex features to web pages.

| Aspect         | ECMAScript                             | JavaScript                            |
|----------------|-----------------------------------------|---------------------------------------|
| Definition     | ECMAScript is a scripting language specification standardized by ECMA International. | JavaScript is a programming language that is an implementation of the ECMAScript specification. |
| Scope          | It defines the rules and guidelines that JavaScript (and other scripting languages) should follow. | It's a specific implementation of ECMAScript, providing the actual language used by developers. |
| Versions       | There have been multiple versions of ECMAScript, each introducing new features, enhancements, and specifications. | It's a particular version or implementation of ECMAScript. For instance, JavaScript ES5, ES6 (also known as ECMAScript 2015), ES7, etc. |
| Standardization| It serves as the standard for scripting languages, providing a guideline for how scripting languages should function. | It's the practical application of the ECMAScript specifications, used in web development and various applications. |
| Usage          | It's the core specification used by various scripting languages, including JavaScript, JScript, and ActionScript. | It's predominantly associated with web browsers and client-side scripting but also used in server-side development via Node.js. |
| Evolution      | Continues to evolve over time, with new versions introducing additional functionalities and improvements. | It evolves as new versions of ECMAScript are released, incorporating new features and enhancements. |

In summary, ECMAScript is a standard specification for scripting languages, while JavaScript is a widely used programming language that implements the ECMAScript specification in practice. JavaScript is just one of the implementations of ECMAScript, adhering to its rules and guidelines.


1. V8 - Used by google chrome/chromium - C
   https://github.com/v8/v8

2. SpiderMonkey - Used by Firefox - C + Rust
   https://spidermonkey.dev/


#### What is Node.js?
- Some smart people took out the V8 engine Added some Backend things (filesystem reads) on top to create a new runtime to compete with BE languages like Java.
- JS was never meant to be run in the backend Eventually became very popular and is a popular choice of runtime on the backend

Node.js is an open-source, server-side runtime environment built on Chrome's V8 JavaScript engine. It enables developers to run JavaScript code on the server-side, outside the web browser. Created by Ryan Dahl in 2009, Node.js has gained widespread popularity due to its ability to handle asynchronous I/O operations efficiently and its event-driven architecture.

Node.js uses an event-driven, non-blocking I/O model, which makes it well-suited for building scalable and high-performance applications. It allows developers to create various types of server-side applications, such as web servers, APIs (Application Programming Interfaces), real-time chat applications, streaming applications, and more.

Key features of Node.js include:

1. Asynchronous and Event-Driven: Node.js uses callbacks and event-driven architecture, allowing multiple I/O operations to be handled concurrently without blocking the execution of other code.

2. NPM (Node Package Manager): Node.js comes with npm, a powerful package manager that hosts a vast ecosystem of open-source libraries and tools. Developers can easily access and integrate third-party modules into their projects.

3. Single Programming Language: Using JavaScript for both client-side and server-side development streamlines the development process, as developers can work with a consistent language across the entire stack.

4. Scalability: Node.js is known for its ability to handle a large number of concurrent connections efficiently, making it suitable for building scalable applications.

#### What is Bun?
Other than the fact that JS is single threaded, Node.js is slow (multiple reasons for it)

Some smart people said they wanted to re-write the JS runtime for the backend and introduced Bun

- It is a significantly faster runtime
- It is written in Zig

https://github.com/oven-sh/bun

### What can you do with Node.js?

1. Create clis
2. Create a video player
3. Create a game
4. Create an HTTP Server

#### What is an HTTP Server?
HTTP- Hyper text transfer Protocol
1. A protocol that is defined for machines to communicate
2. Specifically for websites, it is the most common way for your
website’s frontend to talk to its backend

- Some code that follows the HTTP Protocol And is able to communicate with clients (browsers/mobile apps...)
- Think of it to be similar to the call app in your phone Which lets you communicate with your friends

An HTTP (Hypertext Transfer Protocol) server is a software application or a program that delivers web content in response to requests sent by clients, typically web browsers. It's a foundational component of the World Wide Web and serves as the backbone for communication between clients (such as web browsers) and servers.

When a user enters a URL (Uniform Resource Locator) into a web browser or clicks on a link, the browser sends an HTTP request to the appropriate server. The HTTP server receives this request, processes it, and sends back a response, usually in the form of HTML pages, images, CSS files, JavaScript, or other resources required to render the requested web page in the browser.

HTTP servers utilize the HTTP protocol to handle incoming requests and generate appropriate responses. These servers are responsible for:

1. Receiving HTTP requests: HTTP servers listen for incoming requests on a specific port (usually port 80 for HTTP or port 443 for HTTPS). When a request is received, the server processes the request headers and the requested resource path.

2. Processing requests: Based on the request type (GET, POST, PUT, DELETE, etc.) and the requested URL, the HTTP server determines how to handle the request. It might fetch data from a database, execute server-side code, or retrieve static files stored on the server.

3. Generating responses: After processing the request, the server constructs an HTTP response. This response includes a status code (indicating success or failure), response headers, and the requested content (HTML, images, JSON data, etc.).

Common HTTP servers include Apache HTTP Server, Nginx, Microsoft Internet Information Services (IIS), and Node.js (which can be used as an HTTP server using modules like HTTP or Express).

HTTP servers play a crucial role in enabling the exchange of information on the web by facilitating the request and delivery of web resources between clients and servers.
In the end, its the client throwing some information at a server

Server doing something with that information
Server responding back with the final result

Think of them as functions, where

1. Arguments are something the client sends
2. Rather than calling a function using its name, the client uses a URL
3. Rather than the function body, the server does something with the request
4. Rather than the function returning a value, the server responds with some data


Things client needs to worry about (HTTP Client Node)
- Protocol (http/https)
- Address (url/ip/port)
- Route
- Header body (Query/paramater)
- Method

Things client needs to worry about (HTTP Server Node)
- Responce header 
- Responce body
- Status code

Client
1. Browser parses the URL
2. Does a DNS Lookup (converts google.com to an IP)
3. Establishes a connection to the IP (does handshake...)

What is DNS resolution
- URLs are just like contacts in your phone
- In the end, they map to an IP
- If you ever buy a URL of your own, you will need to point it to the IP of your server

Server
1. You get the inputs (route, body, headers)
2. You do some logic on the input, calculate the output
3. You return the output body, headers and status code

What are the common methods you can send to your BE server?
1. GET
2. POST
3. PUT
4. DELETE

What are the common status codes the backend responds with?
1. 200 - Everything is ok
2. 404 - Page/route not found
3. 403 - Authentication issues
4. 500 - Internal server error

## Library that we are using - Express

https://expressjs.com/en/starter/hello-world.html

Create a simple express server

Notes:- https://quickest-juniper-f9c.notion.site/2-NodeJS-and-ExpressJS-concepts-bd3a6a6cd1c64764bee7865a082fa979
