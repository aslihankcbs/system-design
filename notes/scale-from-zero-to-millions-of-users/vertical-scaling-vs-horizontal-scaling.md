# Vertical Scaling vs Horizontal Scaling


- Vertical scaling involves increasing the power (CPU, RAM, etc.) of existing servers, while horizontal scaling entails adding more servers to the resource pool. 
- Vertical scaling is simpler and effective when traffic is low, but it has limitations such as a hard limit on server capacity and lack of failover. 
- Horizontal scaling, preferred for large-scale applications, addresses these limitations by adding servers and enabling failover and redundancy.

When users connect directly to the web server, resulting in potential downtime if the server fails. 
Additionally, heavy traffic can overwhelm the server, causing slower response times or failures. 
Implementing a load balancer resolves these issues by distributing traffic across multiple servers.