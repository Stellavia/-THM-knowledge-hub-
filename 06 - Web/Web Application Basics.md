🔗 [Link to the Room](https://tryhackme.com/room/webapplicationbasics)

## 🏷️ Learn the basics of web applications: HTTP, URLs, request methods, response codes, and headers.

# 📚 Study Notes 

**== PAGE IN PROGRESS ==**

## Web Application Overview

---  
><details><summary>❓Which component on a computer is responsible for hosting and delivering content for web applications?</summary>web server</details>
---  
><details><summary>❓Which tool is used to access and interact with web applications?</summary>web browser</details>
---  
><details><summary>❓Which component acts as a protective layer, filtering incoming traffic to block malicious attacks, and ensuring the security of the web application?</summary>web application firewall</details>
---

## Uniform Resource Locator

---  
><details><summary>❓Which protocol provides encrypted communication to ensure secure data transmission between a web browser and a web server?</summary>HTTPS</details>
---  
><details><summary>❓What term describes the practice of registeriing domain names that are misspelt variations of popular websites to exploit user errors and potentially engage in faudulent activities?</summary>Typosquatting</details>
---  
><details><summary>❓What part of a URL is used to pass additional information, such as search terms or form inputs, to the web server?</summary>Query String</details>
---

## HTTP Messages

---  
><details><summary>❓Which HTTP message is returned by the web server after processing a client's request?</summary>HTTP response</details>
---  
><details><summary>❓What follows the headers in an HTTP message?</summary>Empty Line</details>
---

## HTTP Request: Request Line and Methods

---  
><details><summary>❓Which HTTP protocol version became widely adopted and remains the most commonly used version for web communication, known for introducing features like persistent connections and chunked transfer encoding?</summary>HTTP/1.1</details>
---  
><details><summary>❓Which HTTP request method describes the communication options for the target resource, allowing clients to determine which HTTP methods are supported by the web server?</summary>OPTIONS</details>
---  
><details><summary>❓In a HTTP request, which component specifies the specific resource or endpoint on the web server that the client is requesting, typically appearing after the domain name in the URL?</summary>URL Path</details>
---

## HTTP Request: Headers and Body

---  
><details><summary>❓Which HTTP request header specifies the domain name of the web server to which the request is being sent?</summary>Host</details>
---  
><details><summary>❓What is the default content type for form submissions in an HTTP request where the data is encoded as key=value pairs in a query string format?</summary>application/x-www-form-urlencoded</details>
---  
><details><summary>❓Which part of an HTTP request contains additional information like host, user agent, and content type, guiding how the web server should process the request?</summary>Request Headers</details>
---

## HTTP Response: Status Line and Status Codes

---  
><details><summary>❓What part of an HTTP response provides the HTTP version, status code, and a brief explanation of the response's outcome?</summary>Status Line</details>
---  
><details><summary>❓Which category of HTTP response codes indicates that the web server encountered an internal issue or is unable to fulfil the client's request?</summary>Server Error Responses</details>
---  
><details><summary>❓Which HTTP status code indicates that the requested resource could not be found on the web server?</summary>404</details>
---

## HTTP Response: Headers and Body

---  
><details><summary>❓Which HTTP response header can reveal information about the web server's software and version, potentially exposing it to security risks if not removed?</summary>server</details>
---  
><details><summary>❓Which flag should be added to cookies in the Set-Cookie HTTP response header to ensure they are only transmitted over HTTPS, protecting them from being exposed during unencrypted transmissions?</summary>Secure</details>
---  
><details><summary>❓Which flag should be added to cookies in the Set-Cookie HTTP response header to prevent then from being accessed via JavaScript, thereby enhancing security against XSS attacks?</summary>HttpOnly</details>
--
## Security Headers

---  
><details><summary>❓In a Content Security Policy (CSP) configuration, which property can be set to define where scripts can be loaded from?</summary>script-src</details>
---  
><details><summary>❓When configuring the Strict-Transport-Security (HSTS) header to ensure that all subdomains of a site also use HTTPS, which directive should be included to apply the security policy to both the main domain and its subdomains?</summary>includeSubDomains</details>
---  
><details><summary>❓Which HTTP header directive is used to prevent browsers from interpreting files as a different MIME type than what is specified by the server, thereby mitigating content type sniffing attacks?</summary>nosniff</details>
---


## Practical Task: Making HTTP Requests

---  
><details><summary>❓Make a GET request to /api/users. What is the flag?</summary>THM{}</details>
---  
><details><summary>❓Make a POST request to /api/user/2 and update the country of Bob from UK to US. What is the flag?</summary>THM{}</details>
---  
><details><summary>❓Make a DELETE request to /api/user/1 to delete the user. What is the flag?</summary>THM{}</details>
---
