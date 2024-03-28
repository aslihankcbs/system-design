# Load Balancer

#### Keywords
- distributes traffic
- web servers
- availability
- no failover

A load balancer evenly distributes incoming traffic among web servers that are defined in a load-balanced set.
With this system, users cannot reach web servers. They only reach public IPs.

For security, private IPs are used for communication between servers (Private IP is an IP address reachable only between servers in the same network. It is unreachable on the internet).
The load balancer communicates with web servers through private IPs.

With a load balancer and adding a second server, we solved no failover and improved the availability of the web tier.
If one server goes offline all the traffic will be routed to other servers. This prevents the website from going offline.

If the website traffic grows rapidly, we can add more servers web server pool and the load balancer automatically starts to send requests to them.