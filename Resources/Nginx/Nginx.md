
- Web  Server
	- Serves web content
- Proxy
	- Load balancing
	- backend routing(reverse proxy)
	- caching


Layer 4 and Layer 7 proxying in Nginx

- Nginx can operate in layer 7 (http) or layer 4 (tcp)
- using _stream_ context it becomes layer 4 proxy
- using _http_ context it becomes layer 7 proxy