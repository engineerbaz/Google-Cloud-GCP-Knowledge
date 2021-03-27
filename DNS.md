# DNS
- Cloud DNS is a high performance, gobal Domain Name System (DNS)
- Cloud DNS API is built around projecs, managed Zones, record sets & changes to record sets.
- A Google Cloud Console project is a container for resources , a domain for access control, and the place where billing is configured/aggregated. 
- Every CD operations must specify the project to work

## Feature 
- Authoritative DNS lookup
  - translates requests for domai name like www.google.com into IP like 45.32.45.122
- Fast Anycast Name server
  - Global IP from redundanct locations around the world.
- Scalability & availability 
- Stackdriver logging
- Manage through API & Web UI 
- Cost 
  - First 1 billion queries = $ 0.4 per million per month
  -Oueries over  1 billion queries = $ 0.2 per million per month
