### What is an API?

A web API allows for information or functionality to be manipulated by other programs via the internet.

In programming more generally, the term API, short for Application Programming Interface, refers to a part of a computer program designed to be used or manipulated by another program, as opposed to an interface designed to be used or manipulated by a human.

Computer programs frequently need to communicate amongst themselves or with the underlying operating sytem, and API's are one way they do it.

### When to create an API

1.  your data set is large, making download via FTP unwiedly or resource-intensive.
2.  your users will need to access your data in realtime, such as for display on another website, or as part of an application.
3.  your data changes or is updated frequently.
4.  your users only need access to a part of the data at any given time.
5.  your users will need to perform actions other than retrieve data, such as contributing, updating, or deleting data.

API's are not always the best way of sharing data with users. If the size of the data you are providing is relatively small, you can instead provide a "data dump" in the form of a downloadable JSON, XML, CSV, or SQLite file.

You can provide both, and individual users may find one or the other to better match their use case.

### API terminology

-   HTTP (HyperText Transfer Protocol) - is the primary means of communicating data on the web. HTTP implements a number of "methods", which tell which direction data is moving and what should happen to it. The two most common are GET, which pulls data from a server, and POST, which pushes new data to a server.
-   URL (Uniform Resource Locator) - a URL consists of a protocol (http://), domain, and optional path (/about). A URL describes the location of a specific resource, such as a web page. When reading about API's, you may see the terms URL,request, URI, or endpoint used to describe adjacent ideas.
-   JSON (Javascript Object Notation) - is a text-based data storage format that is designed to be easy to read for both humans and machines. JSON is generally the most common format for returning data through an API, XML being the second most common.
-   REST (Representational State Transfer) - is a philosophy that describes some best practices for implementing APIs. APIs designed with some or all of these principles in mind are called REST APIs.

### **Programming APIs and Web Services**

Tools: Postman; SoapUI; GraphQL

Data is transfered between client and server with a common web language like XML. Each application can be written in two completely different languages, but they can use XML to communicate the data they need.

Web services type:

-   SOAP(Simple Object Access Protocol) - sends messages using XML. A XML doc is sent with the data in a certain format.
-   REST(Representational State Transfer) - uses HTTP protocol to access resources like docs, pics or videos.

Advantages of web services:

-   Reusability
-   Language transparency
-   Usability
-   Deployability

Considerations of web services

-   Latency - is the time it takes a request to return a response. Latency is something to consider, so that websites and apps have fast response time and good performance.
-   Partial failure - is when a server or network fails to respond. Distributed systems should be designed to handle partial failures.

Secure Web Services

-   Authentication: validates identity of client (user credentials).
-   Authorization: determines level of client's access.
-   Basic Authentication (basic auth): is the simplest protocol available for performing web service authentication over the HTTP protocol. Only requires user and password credentials.

401 status code → which means the request is unauthorized.

-   API key Authentication: requires the API to be accessed with a unique key.

Web Services, APIs and Microservices

APIs - typically have a more lightweight architecture and are good for devices with more limited bandwith.

Web Services - dependent on SOAP protocol; requires more work to pack and unpack data.

Microservices - are fully contained individual components that communicate with each other in calling clients.

REST overview

REST is a set of guidelines used to design APIs.

API Principles

1.  Data and functionality in an API are considered resources, and identified through something called the URI (Uniform Resource Identifier), this are accessed by weblinks.
2.  Resources are manipulated using a fixed set of operations:
    -   GET: retrieves a resource
    -   POST: creates a resource
    -   PUT: updates a resource
    -   DELETE: removes a resource
3.  Resources can be represented in multiple formats, like:
    -   HTML
    -   XML
    -   Plain text
    -   other formats defined by a media type
4.  Communication between the client and endpoint is stateless, meaning the server will not store any state the client made.