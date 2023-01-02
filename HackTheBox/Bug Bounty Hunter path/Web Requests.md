#### HTTP Fundamentals
**HyperText Transfer Protocol (HTTP)**
HTTP is an application-level protocol used to access the WWW resources.

HTTP communication consists of a client and a server, where the client requests the server for a resource. The server processes the requests and returns the requested resource. The default port for HTTP communication is port 80 (though this can be changed to any other port, depending on the web server configuration). The same requests are utilized when we use the internet to visit different websites. We enter a Fully Qualified Domain Name (FQDN) as a Uniform Resource Locator (URL) to reach the desired website.

**URL**
Resources over HTTP are accessed via a URL, which offers many more specifications than simply specifying a website we want to visit.
Here is what each component stands for:
![[Screenshot 2022-03-30 at 16.50.58.png]]
Not all components are required to access a resource. The main mandatory fields are the scheme and the host, without which the request would have no resource to request.

**HTTP flow**
The first time a user enters the URL into the browser, it sends a request to a DNS (Domain Name Server) to resolve the domain and get its IP. The DNS server looks up the IP address for the URL and returns it. All domain names need to be resolved this way, as a server can't communicate without an IP address.
Once the browser gets the IP address linked to the requested domain, it sends a GET request to the default HTTP port (e.g. 80), asking for the root / path. then, the web server receives the request and processes it. By default, servers are configured to return an index file when a request for / is received.
The contents of the / are read and returned by the web server as an HTTP response. The response also contains the status code (e.g. 200 OK), which indicates that the request was successfully processed. The web browser then renders the / contents and presents it to the user.

**cURL (client URL)** 
is a command-line tool and library that primarily supports HTTP along with many other protocols. This makes it a good candidate for scripts as well as automation, making it essential for sending various types of web requests from the command line, which is necessary for many types of web penetration tests.
We can send a basic HTTP request to any URL by using it as an argument:
$ `curl inlanefreight.com`
The cURL does not render the HTML/JavaScript/CSS code, unlike a web browser, but prints it in its raw format. As Penetration Testers, we are mainly interested in the request and response context, which usually becomes much faster and more convenient than a web browser.

We may also use cURL to download a page or a file and output the content into a file using the -O flag. If we want to specify the output file name, we can use the -o flag and specify the name. Otherwise, we can use -O and cURL will use the remote file name, as follows:
$ `curl -O inlanefreight.com/index.html`

**Hypertext Transfer Protocol Secure (HTTPS)**
One of the significant drawbacks of HTTP is that all data is transferred in clear-text. This means that anyone between the source and destination can perform a Man-in-the-Middle (MitM) attack to view the transferred data.
To counter this issue, the HTTPS protocol was created, in which all communications are transferred in an encrypted format, so even if a third party does intercept the request, they would not be able to extract the data out of it.

_Note:_ although the data transferred through the HTTPS protocol may be encrypted, the request may still reveal the visited URL if it contacted a clear-text DNS server. For this reason, it is recommended to utilize encrypted DNS servers (e.g. 8.8.8.8 or 1.2.3.4), or utilize a VPN service to ensure all traffic is properly encrypted.

**HTTPS flow**
The client (web browser) sends a "client hello" packet, giving information about itself. After this, the server replies with "server hello", followed by a key exchange (is a method in cryptography by which cryptographic keys are exchanged between two parties, allowing use of a cryptographic algorithm) to exchange SSL certificates. The client verifies the key/certificate and sends one of its own. After this, an encrypted handshake is initiated to confirm whether the encryption and transfer are working correctly. 
Once the handshake completes successfully, normal HTTP communication is continued, which is encrypted after that.

**cURL for HTTPS**
cURL should automatically handle all HTTPS communication standards and perform a secure handshake and then encrypt and decrypt data automatically. However, if we ever contact a website with an invalid SSL certificate or an outdated one, then cURL by default would not proceed with the communication to protect against MitM attacks.
To skip the certificate check with cURL, we can use the -k flag:
$ `curl -k https://inlanefreight.com`

**HTTP Requests and Responses**
HTTP communications mainly consist of an HTTP request and an HTTP response. An HTTP request is made by the client (cURL/browser), and is processed by the server. The requests contain all of the details we require from the server, including the resource (URL, path, parameters), any request data, headers or options we specify, and many other options.
Once the server receives the HTTP request, it processes the requests and responds by sending the HTTP response, which contains the response code, as discussed in a later section, and may contain the resource data if the requester had access to it.

- **_HTTP Request_**
![[Screenshot 2022-03-31 at 13.42.05.png]]
The image above shows an HTTP GET request to the URL:
	http://inlanefreight.com/users/login.html

The first line of any HTTP request contains three main fields:
![[Screenshot 2022-03-31 at 13.43.15.png]]
The next set of lines contain HTTP header value pairs, like Host, User-Agent, Cookie, and many other possible headers. These headers are used to specify various attributes of a request. The headers are terminated with a new line, which is necessary for the server to validate the request. Finally, a request may end with the request body and data.

- **_HTTP Response_**
Once the server processes our request, it sends its response. The following is an example HTTP response:
![[Screenshot 2022-03-31 at 13.53.14.png]]
The first line of an HTTP response contains two fields. The first being the HTTP version, and the second denotes the HTTP response code.
Response codes are used to determine the request's status, as will be discussed in a later section. After the first line, the response lists its headers, similar to an HTTP request.
Finally, the response may end with a response body, which is separated by a new line after the headers. The response body is usually defined as HTML code. However, it can also respond with other code types such as JSON, website resources such as images, style sheets or scripts, or even a document such as a PDF document hosted on the webserver.

**cURL**
cURL also allows us to preview the full HTTP request and the full HTTP response. To view the full HTTP request and response, we can simply add the -v verbose flag to our earlier commands, and it should print both the request and response:
$ `curl inlanefreight.com -v`
_Note:_ the -vvv flag shows an even more verbose output.

**HTTP Headers**
HTTP headers pass information between the client and the server. Some headers are only used with either requests or responses, while some other general headers are common to both.
Headers can have one or multiple values, appended after the header name and separated by a colon.
We can divide headers into the following categories:
- **_General Headers:_** are used in both HTTP requests and responses. They are contextual and are used to describe the message rather than its contents.![[Screenshot 2022-03-31 at 14.42.07.png]]
- **_Entity Headers:_** can be common to both the request and response. These headers are used to describe the content (entity) transferred by a message. They are usually found in responses and POST or PUT requests.![[Screenshot 2022-03-31 at 14.44.24.png]]
- **_Request Headers:_** the client sends Request Headers in an HTTP transaction. These headers are used in an HTTP request and do not relate to the content of the message. The following headers are commonly seen in HTTP requests: ![[Screenshot 2022-03-31 at 14.47.04.png]]
- **_Response Headers:_** can be used in an HTTP response and do not realte to the content. Certain response headers such as Age, Location, and Server are used to provide more context about the response. The following headers are commonly seen in HTTP responses. ![[Screenshot 2022-03-31 at 14.49.30.png]]
- **_Security Headers:_** with the increase in the variety of browsers and web-based attacks, defining certain headers that enhanced security was necessary. HTTP Security Headers are a class of response headers used to specify certain rules and policies to be followed by the browser while accessing the website. ![[Screenshot 2022-03-31 at 15.06.09.png]]
_Note: this section only mentions a small subset of commonly seen HTTP headers._

#### HTTP Methods and Codes
In the HTTP protocol, several request methods allow the browser to send information, forms, or files to the server. These methods are used, among other things, to tell the server how to process the request we send and how to reply.

**Request Methods**
The following are some of the commonly used methods
![[Screenshot 2022-03-31 at 16.39.46.png]]
_The list only highlights a few of the most commonly used HTTP methods. The availability of a particular method depends on the server as well as the application configuration._ 

_Note:_ most modern web applications mainly rely on the GET and POST methods. However, any web application that utilizes REST APIs also rely on PUT and DELETE, which are used to update and delete data on the API endpoint, respectively.

**Response Codes**
HTTP status codes are used to tell the client the status of their request. An HTTP server can return five types of response codes:
![[Screenshot 2022-04-01 at 10.51.32.png]]
The following are some of the commonly seen examples from each of the above HTTP method types:
![[Screenshot 2022-04-01 at 10.52.16.png]]

**GET**
Whenever we visit any URL, our browser default to a GET request to obtain the remote resources hosted at that URL. Once the browser receives the initial page it is requesting; it may send other requests using various HTTP methods. 

**HTTP Basic Auth**
Unlike the usual login forms, which utilize HTTP parameters to validate the user credentials (e.g. POST request), this type of authentication utilizes a basic HTTP authentication, which is handled directly by the webserver to protect a specific page/directory, without directly interacting with the web application.
To provide the credentials through cURL, we can use the -u flag:
$`curl -u admin:admin http://<SERVER_IP>:<PORT>/`
or:
$`curl http://admin:admin@<SERVER_IP>:<PORT>/`

Most modern web applications use login forms built with the backend scripting language, which utilize HTTP POST requests to authenticate the users and then return a cookie to maintain their authentication.

**GET Parameters**


#### POST
we saw how GET requests may be used by web application for functionalities like search and accessing pages. Whenever web applications need to transfer files or move the user parameters from the URL, they utilize POST requests.
Unlike HTTP GET, which places user parameters within the URL, HTTP POST places user parameters within the HTTP Request body. This has three main benefits:
- _Lack of Logging:_ as POST requests may transfer large files, it would not be efficient for the server to log all uploaded files as part of the requested URL, as would be the case with a file uploaded through a GET request.
- _Less Encoding Requirements:_ URLs are designed to be shared, which means they need to conform to characters that can be converted to letters. The POST request places data in the body which can accept binary data. The only characters that need to be encoded are those that are used to separate parameters.
- _More data can be sent:_ the maximum URL lenght varies between browsers, web servers (Apache, nginx), Content Delivery Networks (Fastly, Cloudflare), and even URL Shortners. Generally speaking, URL's should be kept to below 2000 characters.










