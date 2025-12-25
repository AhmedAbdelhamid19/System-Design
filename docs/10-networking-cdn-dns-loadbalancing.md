# 10 - Networking: CDN, DNS, Load Balancers, Geo Routing

## CDN (Content Delivery Network)

- Network of servers around the world that cache static content (images, video, CSS, JS) close to users.
- Speeds up loading time, reduces origin traffic, and lowers latency for static assets.
- for example if User from Germany wants image logo.png so CDN checks nearest server, If cached then returns immediately (super-fast), if not then fetches from your origin server, caches it, returns it, so Next German user gets it instantly from local CDN node
- one of most popular CDNs is Cloudflare.

## DNS (Domain Name System)

- The internet’s phonebook: maps human-friendly domain names to IP addresses.
- DNS with geo routing can return an IP that directs users to a nearby region.

## Load Balancer vs Geo Routing vs DNS

- Load Balancer: routes traffic across servers within a datacenter or region (decides which server handles a request).
- Geo routing: decides which region/endpoint the user should be sent to (region-level routing).
- DNS: translates domain name to IP and can be used to return region-specific IPs when geo routing is enabled.
