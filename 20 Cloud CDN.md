# Google Cloud CDN
- Content Delivery Network (CDN) uses Google's globally distributed edge point of presence (POP) to cache HTTP(S) LoadBalanced Content to closes location 
- Caching at edge  of Google's network provides faster Delivery of Content to your users while reducing serving cost.
- The HTTP LoadBalancer provides the frontend IP address and port that recieve request and the backend reponds to queries
- Backend (Origin Server) can be 
  - Instance Group
  - NEG (Network Endpoint Group)
  - Bucket in Google Storage
- 