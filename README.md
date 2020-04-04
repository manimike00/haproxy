HAProxy Architecture

Frontend - front of haproxy

	Timeout Client (how long to wait for client)
	Bind (Which Port to listen)
	ACL (Access Control List i.e, conditions path)

Backend - behind haproxy
	
	Timeout Connect
	Timeout Server
	Balance (roundrobin, leastconn, source)

Usecases:
	
	Multiple Frontends or Multiple Backends
	Frontend bind to one or more ports
	Frontend connects to a backend

Haproxy modes (TCP and HTTP)

	Frontend & Backend can have mode of protocol
	Which layer they work on Layer 4 (tcp) layer 7 (http)
	Using mode tcp becomes layer 4 proxy
	Using mode http becomes layer 7 proxy

Create Certificate
```
  $ sudo certbot certonly --standalone 
  $ sudo cat path/fullchain.pem path/privkey.pem | sudo tee /etc/ssl/haproxy.pem
