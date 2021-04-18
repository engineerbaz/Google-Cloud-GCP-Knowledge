

Recently a major BGP leak disrupts thousands of networks globally.


The two main differences between those time of events were described as:

Routes redirected through wrong ASNs/links (Route leaks), described as types 1-4 RFC 7908;
Routes redirected to wrong ASNs (Hijack), described as types 5 and 6 RFC 7908.
During a BGP route leak, traffic destined to your network will most likely flow in an inefficient way, which could lead to increased network latency and packet loss. Nevertheless, it will reach your network almost certainly if there is no critical network congestion due to some reason (like the bad intention of a malfunctor).

During a BGP Hijack, traffic destined to your network is rerouted to a third party and stays there.


1. Setting MAXPREF: 
2. Configuring filters:
3. Deploying RPKI: 




Take care of your BGP's configuration, it will take care of your Network & protect resources.