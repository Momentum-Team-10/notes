`autoscale: true`
# [fit] Using JavaScript To Make API Requests

---

Agenda

1. what is http?
2. Request-response overview and diagram
3. URL anatomy and resources
4. A closer look at an HTTP request and response
5. HTTP verbs

---

QUESTION: who knows who invented the http protocol?

[Julia Evans zine on networking](https://jvns.ca/networking-zine.pdf)
[HTTP Basics](http://www.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html)

---

## HTTP Request/Response Cycle

![inline](https://www.cdnfinder.com/wp-content/uploads/2018/12/HTTP-Request-and-Response-Over-Web-1.png)

---

## URL is uniform resource locator

HTTP is used to transmit resources, not just files. A resource is some chunk of information that can be identified by a URL (it's the R in URL). The most common kind of resource is a file, but a resource may also be a dynamically-generated query result, the output of a CGI script, a document that is available in several languages, or something else.

Right now it may help to think of a resource as similar to a file, but more general. A resource is a high-level description of the thing you’re trying to get hold of when you submit a request. A noun.

---

# URL anatomy

http://www.google.com/maps/index.html?search=tacos&zip=27701
protocol / subdomain.domain.top-level-domain/path/query-string-parameters

- protocol
- subdomain, domain, top-level domain
- path
- query string parameters
  - `?` the start of the query string
  - `key=value` param pair
  - `&` used to add additional query params
- ACSII encoding: only characters in the [ASCII](https://en.wikipedia.org/wiki/ASCII) char set
- e.g. space represented as `%20`

- Protocol is just a set of rules for communication
- HTTP follows a request response model
- [draw diagram of client-server req-response]
- stateless: that means it does not hold state (or data)
- each req/response pair is completely independent of the previous one
  - because of that reality, if you want to hold state in a web application, you have to create a mechanism to do that somehow (session, cookies)

---

# An HTTP Request

A text-based message that follows a standard format

An HTTP request has three parts:

1. request line
2. request headers
3. request message body

---

What is it? Packet of info!

How do you send one? browser, from the web page using AJAX, from a tool like Postman, or from the cli with cURL

- every request gets a response, even if it is an error

---

## HTTP Request Structure

- [http request examples](https://www.tutorialspoint.com/http/http_requests.html)
- [http messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages)

Headers -- let the client(browser) and server (api) pass additional information with an HTTP request or response

Request Header: This type of headers contains information about the fetched request by the client.
Response Header: This type of headers contains the location of the source that has been requested by the client.

(look at an example: headers, etc)

---

### Request: http verbs

[GitHub API docs: http verbs](https://developer.github.com/v3/#http-verbs)

- GET -> ask for some stuff, get some data back in the form of JSON or HTML
- POST -> send some stuff to the server, get a response back that says it went well or didn't
- PUT/PATCH -> update some stuff on the server
- DELETE -> get rid of some stuff on the server

---

DEMO JavaScript weekly reqs and resps

### Request/Response: http headers

[http headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

---

## HTTPv Status Codes

the meaning of a HTTP response code is not extremely precise; this is a consequence of HTTP itself being rather generic. You should attempt to use the response code which most closely matches the situation at hand.

- [http status codes]http://www.restapitutorial.com/httpstatuscodes.html
- [http tweet]https://twitter.com/stevelosh/status/372740571749572610

---

## Resources

[Insomnia](https://insomnia.rest/)

[Pokemon API](https://pokeapi.co/)
[GitHub REST API](https://developer.github.com/v3/)

[MDN on HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
[Eloquent JavaScript Chapter 18: HTTP and Forms](https://eloquentjavascript.net/18_http.html)