# Load Balancer Notes

## Keywords
- Distributes traffic
- Web servers
- Availability
- No failover

A load balancer evenly distributes incoming traffic among web servers that are defined in a load-balanced set. Users cannot directly reach the web servers; they only interact with public IPs.

For security reasons, private IPs are used for communication between servers. Private IPs are only reachable within the same network and are not accessible over the internet. The load balancer communicates with web servers through these private IPs.

By implementing a load balancer and adding a second server, we have addressed the issue of no failover and significantly improved the availability of the web tier. In the event that one server goes offline, all traffic is automatically rerouted to other servers, preventing the website from becoming inaccessible.

In the case of rapid website traffic growth, we can easily scale by adding more servers to the web server pool. The load balancer will automatically start directing requests to these additional servers, ensuring efficient distribution of traffic.