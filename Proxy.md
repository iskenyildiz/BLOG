# Proxy


If we use a proxy server, internet traffic flows through the proxy server on its way to  the address we requested. Proxy server acts as a firewall to speed up requests. When we make a web request the request goes to the proxy server then proxy collects the responses and forwards us the web page.

VPNs are good for masking your activity online. In contrast, a proxy server doesn’t anonymize your activity until your data reaches the server itself.

## Why should we use a proxy server?

- An advantage of proxy is that it can cache frequent requests from its hard disk which improve user overall response time for internet surfing.

- Illegal usage of proxy can lead to anonymous surfing on the web which enables user privacy.

- Proxy can also be used to monitor traffic.

- Using proxies for web scraping, this is more for businesses, we need proxies when scraping so we just don’t get IP blocked.

## Forward and reverse proxy servers

Forward proxies send requests of client to the web server.

Reverse proxy is the server that sits in front of web servers and forwards client requests to those web servers.

Forward proxies make sure no origin servers communicate directly with the specified client server.

Reverse proxies are used to make sure no client server directly communicates with the origin server.

Open proxy is accessible by any internet user that changes their IP address once used.

An origin server is the server that responds to client requests. 

DNS proxies forward DNS requests from LANs to DNS servers while caching for increased speed. 

The only real privacy element of a proxy is that they hide our IP address. There aren’t any encryption elements like in a VPN so our traffic can be accessed. To fully stay protected in the long term, VPN is the greater solution if one can afford its processing and money costs.
 VPN is also inserted to the operating system so it captures all the traffic from our system instead of a proxy which only protects whatever application it is attached to(HTTP, SSL, FTP etc.)

## HAPROXY

 HAProxy, which stands for High Availability Proxy, is a popular open source software TCP/HTTP (layer 4 and layer 7) Load Balancer and proxying solution which can be run on Linux.

The round robin method, the load balancing default cycles through a list of servers in sequential order.

Leastconn selects the server with the least number of connections. Not recommended for longer sessions.


