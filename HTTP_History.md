**Evolution of HTTP**

   HTTP (HyperText Transfer Protocol) is the underlying protocol of the World Wide Web.

**1. HTTP/0.9 – The one-line protocol**
  
   HTTP/0.9 is extremely simple: requests consist of a single line and start with the only possible method GET followed by the path to the resource
   
    Request 
    GET /mypage.html
    
    Response
    
     <HTML>
     A very simple HTML page
     </HTML>
     
  **2. HTTP/1.0 – Building extensibility**
 
     a) Versioning information is now sent within each request (HTTP/1.0 is appended to the GET line).
     b) A status code line is also sent at the beginning of the response, allowing the browser itself to understand the success or failure of the request and to adapt its behavior in consequence
    
     Request 
    
       GET /mypage.html HTTP/1.0
       User-Agent: chrome/92.0 (Windows 10.1)
    
     Response:
    
       200 OK
       Date: Tue, 30 Nov 2020 08:12:31 GMT
       Server: CERN/3.0 libwww/10.17
       Content-Type: text/html
       <HTML>
       A page with an image
      <IMG SRC="/myimage.gif">
      </HTML>  
     
  **3. HTTP/1.1 – The standardized protocol**
  
      a).A connection can be reused, saving the time to reopen it numerous times to display the resources embedded into the single original document retrieved.
      b).Pipelining has been added, allowing to send a second request before the answer for the first one is fully transmitted, lowering the latency of the communication.
      c).Chunked responses are now also supported.
      d).Additional cache control mechanisms have been introduced.
      e).Content negotiation, including language, encoding, or type, has been introduced, and allows a client and a server to agree on the most adequate content to exchange.
      f).Thanks to the Host header, the ability to host different domains at the same IP address now allows server colocation.
      
     **Request**
       GET /en-US/docs/Glossary/Simple_header HTTP/1.1
       Host: google.com
       User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
       Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
       Accept-Language: en-US,en;q=0.5
       Accept-Encoding: gzip, deflate, br
       Referer: https://google.com

    **Response**
       
       200 OK
       Connection: Keep-Alive
       Content-Encoding: gzip
       Content-Type: text/html; charset=utf-8
       Date: Wed, 20 Jul 2016 10:55:30 GMT
       Etag: "547fa7e369ef56031dd3bff2ace9fc0832eb251a"
       Keep-Alive: timeout=5, max=1000
       Last-Modified: Tue, 19 Jul 2016 00:59:33 GMT
       Server: Apache
       Transfer-Encoding: chunked
       Vary: Cookie, Accept-Encoding
       
       
   **4. HTTP/2 – A protocol for greater performance** 
   
   
     a).It is a binary protocol rather than text. It can no longer be read and created manually. Despite this hurdle, improved optimization techniques can now be implemented.
     b).It is a multiplexed protocol. Parallel requests can be handled over the same connection, removing the order and blocking constraints of the HTTP/1.x protocol.
     c).It compresses headers. As these are often similar among a set of requests, this removes duplication and overhead of data transmitted.
     d).It allows a server to populate data in a client cache, in advance of it being required, through a mechanism called the server push.
     
     
   **5. Post-HTTP/2 evolution**
   
      a).Support of Alt-Svc allows the dissociation of the identification and the location of a given resource, allowing for a smarter CDN caching mechanism.
      b).The introduction of Client-Hints allows the browser, or client, to proactively communicate information about its requirements, or hardware constraints, to the server.
      c).The introduction of security-related prefixes in the Cookie header, now helps guarantee a secure cookie has not been altered.
    
  
