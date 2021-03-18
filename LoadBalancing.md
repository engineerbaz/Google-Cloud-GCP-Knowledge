# LoadBalancing
- World wide auto scalling & LoadBalancing
- scale application on GCE from Zero to full throttle wih GC-LB 
- Distribute LoadBalanced CE resource in single or multiple regions close to users and to meet HA requirement
- CLB can put resources behind a single anycast IP & scale resources up or down with intelligent AutoScaling
- Global LoadBalancing with integrated with Google Cloud CDN for optimal app and Content delivery.

## Global LoadBalancing with Single AnyCast IP
- A single AnyCast IP front-ends all backend instances in regions. 
- Provides cross-region LoadBalancing including auomatic multi-region failover which gently moves traffic in fractions if backend becomes unhealthy.
## Software definded LoadBalancing
- Cloud LoadBalancing is a fully distributed, Software based, managed service for all traffic
  - HTTP/HTTPs
  - TCP/SSL
  - UDP
- Over a million queries per second
- Traffic enters cloud LoadBalancing through 80+ distinct Global LoadBalancing locations.
- Seamless AutoScaling, not require pre-warming, can be scaled from 0 to full.
- Internal LoadBalancing (without exposing to internet)
  - It is architectured using Andromeda, Google's SDN virtualization Platform
  - Also support client across VPN.
- Support for Cutting edge Protocol
  - HTTP/2 with gRPC when connecting to backend
  - 1st Public CSP to provide QUIC Support for HTTPS 
- HTTP(S) for SSL termination
- Affinity
  - provides ability to direct and stick user traffic to specific backend instance
- TCP/SSL LoadBalancing
  - TCP LoadBalancing can spread traffic over a pool of instance within a Compute Engine region.
- Hi Fi Health Check 
- SSL Offload 
  - enables to centrally manage SSL certificate and decryption. 
  - enables encryption between LoadBalancing layer and backends to ensure the highest level of security.
- Cloud CDN 
- UDP LoadBalancing
- Advanced Feature
  - IPv6, Global LoadBalancing, WebSocket, user-definded request headers, and Protocol forwarding for private VIPs.
- stackdriver logging 
  - logs of all the LoadBalancing request sent to LB 
  - For debugging.


----