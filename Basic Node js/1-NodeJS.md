# What Is NodeJS

# topic includes -
 ## NodeJS
 ## Architecture
 ## I/O
## Non-Blocking I/O (Asynchronous)
## Blocking I/O (Synchronous)

### article link [article](https://medium.com/@michaelhenderson/what-is-nodejs-and-why-you-need-to-learn-it-f0760ba9a76a#:~:text=Node.,intensive%2C%20real%2Dtime%20applications.)

`Node.js is a framework for writing server-side JavaScript applications. It is built on top of the V8 JavaScript runtime and uses an event-driven, non-blocking I/O model that makes it perfect for data-intensive, real-time applications.`

Some of the leading companies in the world use Node in production, like Netflix, Paypal, Walmart, and Uber.

Node is often used to build back end services that communicate with client-side applications. These applications get and send data through a back end service called an API.

# Architecture
`Every browser has their own Javascript engine that converts javascript into code that a computer can understand. For example, Microsoft Edge uses Chakra, Firefox uses spidermonkey, and chrome uses V8. This explains why JavaScript code can behave differently in other browsers.`

# What is I/O ? [more](./2-IO.md)
shorthand for Input and Output and it means accessing anything outside of your application. Once an application has started, it is loaded into the machine’s memory. That’s what the CPU will mostly use for running your program. I/O is

Accessing memory is pretty fast, hence a lot of caching mechanisms simply use RAM to store data. However, applications will often need to access the network or read from a text file, and these types of I/O are by far the slowest types. That’s where non-blocking I/O proves it’s dominance.

# Non-Blocking I/O (Asynchronous)
Asynchronous, non-blocking servers, like ones made in Node, only use one thread to service all requests. This means an instance of Node makes the most out of a single thread. This means the server can serve a lot of request without requiring more server hardware; which is expensive.

When requests arrive at the server, they are serviced one at a time. However, when the code serviced needs to query the DB for example, it sends the callback to a second queue and the main request continues to run; it doesn’t wait. Now when the DB operation completes and returns, the corresponding callback is pulled out of the second queue and queued in a third queue where they are pending execution. When the engine gets a chance to execute something else, it picks up a callback from the third queue and executes it.

# Blocking I/O (Synchronous)
Synchronous blocking operations is how some web servers, like ones in ASP.NET, handle IO or network requests by default. If your code reads from a file or the database, your code “blocks” everything after it from executing until that first request is finished. In that period, your machine is holding onto memory and processing time for a thread that is idle.

In order to cater other requests while that thread has stalled depends on your software. Most server software spawns more threads to handle the additional requests. This causes more memory and processing to be consumed.

I am not saying that ASP.NET and other types of frameworks can’t run code asynchronously, they can , but you have to write more code to make it happen. Node runs asynchronously by default without writing extra code.



### Key features of Node.js include:

Asynchronous and Non-blocking I/O: Node.js uses an event-driven architecture, which allows it to handle multiple concurrent connections efficiently. It can handle I/O operations asynchronously, meaning it does not block the execution of other tasks while waiting for a response from an external resource, such as a database or network request.

Fast and Efficient: Node.js leverages the V8 engine, which compiles JavaScript code to native machine code, making it highly performant. Its non-blocking I/O model also contributes to its efficiency by utilizing resources more effectively.

Package Ecosystem: Node.js has a vast ecosystem of open-source packages available through npm (Node Package Manager). Developers can easily access and integrate these packages into their projects, saving time and effort.

Scalability: Due to its non-blocking I/O and event-driven architecture, Node.js can handle a large number of concurrent connections, making it suitable for building scalable applications.

Community Support: Node.js has a large and active community of developers, which contributes to the ongoing improvement and expansion of the platform.

Node.js is commonly used for building web servers, real-time applications (e.g., chat applications, online gaming), RESTful APIs, and microservices. It has gained immense popularity in the web development community and continues to be widely adopted for a variety of projects.