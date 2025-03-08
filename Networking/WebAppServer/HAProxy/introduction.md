HAP Roxy, which stands for High Availability Proxy, is an open-source software solution that provides high availability, load balancing, and proxying for TCP and HTTP-based applications. It is commonly used to distribute incoming network traffic across multiple servers to ensure that no single server bears too much load, thereby improving the reliability and availability of the application.

1. **Load Balancing:** HAProxy distributes incoming requests among a set of backend servers based on various algorithms (round-robin, least connections, etc.). This helps distribute the load evenly and ensures optimal utilization of resources.

1. Frontend : (client <==> HAProxy):

- Timeout Client : time you give to client
- Bind : whish address give and which port IP:PORT
- ACL :

[Access Control List (ACL)](https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts#access-control-list-acl) __Applies frontend or backend__

In relation to load balancing, ACLs are used to test some condition and perform an action (e.g. select a server, or block a request) based on the test result. Use of ACLs allows flexible network traffic forwarding based on a variety of factors like pattern-matching and the number of connections to a backend, for example.

Example of an ACL:   acl url_blog path_beg /blog

This ACL is matched if the path of a user’s request begins with /blog. This would match a request of [http://yourdomain.com/blog/blog-entry-1](http://yourdomain.com/blog/blog-entry-1), for example.

For a detailed guide on ACL usage, check out the [HAProxy Configuration Manual](https://www.haproxy.com/documentation/hapee/latest/configuration/acls/syntax/).

- Frontend always connect to backend.  EX : default_backend my_backend

1. Backend : (HAProxy <==> servers)

- Timeout Connect : how match time you wanna give to that connexon
- Timeout Server : running time
- Balance (round robin, leastconn, source)

2. **High Availability:** HAProxy can be configured in high availability setups where multiple instances of HAProxy work together to ensure that if one instance fails, another can take over seamlessly, preventing downtime.

3. **Proxying:** HAProxy can act as a reverse proxy, forwarding requests from clients to backend servers. It can also perform SSL termination, offloading the SSL/TLS encryption and decryption process from backend servers.

4. **Health Checking:** HAProxy regularly checks the health of backend servers to ensure that it only directs traffic to healthy and operational servers. If a server becomes unavailable, HAProxy can automatically reroute traffic to healthy servers.

5. **Security:** HAProxy provides features like access control, request filtering, and rate limiting to enhance the security of the applications it serves.

6. **Logging and Monitoring:** HAProxy logs can be configured to capture information about incoming requests, response times, and server health. This information is valuable for monitoring and troubleshooting purposes.

7. **TCP and HTTP Support:** HAProxy supports both TCP and HTTP protocols, making it versatile for a wide range of applications.

1. HAProxy modes (TCP and HTTP):

- Frontend and backend can have mode of protocol
- Which layer they work on layer 4 (TCP) layer 7 (https)
- Using mode TCP becomes layer 4 proxy
- Using mode HTTP becomes Layer 7 proxy

HAProxy is widely used in scenarios where high availability, scalability, and efficient load balancing are crucial, such as in web applications, APIs, and microservices architectures. It is known for its performance, flexibility, and the ability to handle a large number of concurrent connections.

1. HAProxy Architecture 

- Multiple Frontends or Backends
- Frontend bind to one or more ports
- A Frontend connects to a backend
- E . G Two Frontends

- Frontend - http binds 80 (forwards to https backend)
- Frontends - https - binds 443