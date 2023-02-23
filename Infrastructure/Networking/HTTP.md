Hypertext transfer protocol (HTTP) is an [application-layer](7.%20Application.md) protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes. HTTP follows a classical [client-server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model), with a client opening a connection to make a request, then waiting until it receives a response. HTTP is a [stateless protocol](https://en.wikipedia.org/wiki/Stateless_protocol), meaning that the server does not keep any data (state) between two requests.

## Methods
HTTP defines a set of **request methods** to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as _HTTP verbs_. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be [safe](https://developer.mozilla.org/en-US/docs/Glossary/Safe/HTTP), [idempotent](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent), or [cacheable](https://developer.mozilla.org/en-US/docs/Glossary/Cacheable).
- [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) - The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data.
- [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) - The `HEAD` method asks for a response identical to a `GET` request, but without the response body.
- [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) - The `POST` method submits an entity to the specified resource, often causing a change in state or side effects on the server.
- [`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) - The `PUT` method replaces all current representations of the target resource with the request payload.
- [`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) - The `DELETE` method deletes the specified resource.
- [`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT) - The `CONNECT` method establishes a tunnel to the server identified by the target resource.
- [`OPTIONS`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS) - The `OPTIONS` method describes the communication options for the target resource.
- [`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE) - The `TRACE` method performs a message loop-back test along the path to the target resource.
- [`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) - The `PATCH` method applies partial modifications to a resource.

## Status codes
When looking at requests, we can check on the _Status Code_ of the request to get some information if the request was successful or not.
- **1XX**: Informational responses. There are very rare.
- **2XX**: Successful responses.
- **3XX**: Redirection messages. These are typically invisible because the browser or HTTP client will automatically do the redirect.
- **4XX**: Client errors. 
- **5XX**: Server errors.

## HTTPS
Hypertext Transfer Protocol _Secure_ or [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https) is an extension of the HTTP protocol. HTTPS secures the data transfer between client and server by [encrypting](https://developer.mozilla.org/en-US/docs/Glossary/Encryption) all of the communication. HTTPS allows a client to safely share sensitive information with the server through an HTTP request, such as credit card information, passwords, or bank account numbers.

### Security and encryption
HTTPS requires that the client use [SSL](https://developer.mozilla.org/en-US/docs/Glossary/SSL) or [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS) to protect requests and traffic by encrypting the information in the request. HTTPS is just HTTP with extra security!

#### HTTPS keeps your messages private, but not your identity
It's important to note that while HTTPS encrypts _what you are saying_, it doesn't necessarily protect _who you are_. Tools like [VPNs](https://nordvpn.com/what-is-a-vpn/) are needed for remaining anonymous online.

#### HTTPS ensures that you're talking to the right person (or server)

In addition to encrypting the information within a request, HTTPS uses [digital signatures](https://en.wikipedia.org/wiki/Digital_signature) to prove that you're communicating with the server that you think you are. If a hacker were to intercept an HTTPS request by tapping into a network cable, they wouldn't be able to successfully pretend they are your bank's web server.
