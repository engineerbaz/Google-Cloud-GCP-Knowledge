# BGP - a network lifeline, Prevent it!

// Recently a major BGP leak disrupts thousands of networks globally.

Few days back, a large BGP routing leak that occurred disrupted the connectivity for thousands of major networks and websites around the world.

Although this BGP routing leak occurred in an ISP's autonomous network (AS55410) based in asia, but it has impacted several companies around the world.

[leak](https://www.bleepstatic.com/images/news/u/1164866/2021/Apr%202021/bgp%20leak/george%20tweet.jpeg)

This issue existed for 10 odd minutes though, but countless users around the world suffers internet connection problem. 

## Is BGP not Safe?
Before knowing if Border Gateway Protocol (BGP, a widely adopted protocol for Internet {Internetwork of networks}) , we need to look what it is and risk associated with it.

## What is BGP? BGP Hijaking & BGP Leaking

### BGP
BGP or Border Gateway Protocol is the protocol used to exchange reachability information between networks and build a “roadmap” of the Internet – simply it is what makes the modern-day internet work.

#### Issue with BGP 

On Internet,  different nodes (autonomous systems) advertise pool of IPs they manage and the traffic they are able to route and every network has a unique number allocated known as Autonomous System Number (ASN), used as representation of that network.

BGP is fragile and does not embed any security protocols, Without additional controls, this  information of route accepted with mistakes can be intercepted, or can be blackholed altogether.

### Hijacking of BGP

BGP route hijacking occurs when a malicious entity manages to "falsely advertise" to other routers. During this, traffic destined to your network is rerouted to a third party and stays there, creates trouble on the Internet and lead to delays, traffic congestion, or total outages.


### BGP Leaking

In route leaking, traffic of your network is redirected to wrong path/network & likely flow in an inefficient way, which could lead to increased network latency and packet loss. Nevertheless, it will reach your network almost certainly if there is no critical network congestion due to some reason

#### Leaking Vs Hijacking 
The two main differences between both are  described as:

    - Routes redirected through wrong ASNs/links (Route leaks), described as types 1-4 RFC 7908;
    - Routes redirected to wrong ASNs (Hijack), described as types 5 and 6 RFC 7908.


## Securing Network by securing BGP

Security of network is cricuical for maintaining network reliability , it is not an One-time task but a on-going process, which should be continue 
Some common safeguards that companies can use to protect against BGP leaks:

1. Deploy RPKI
2. Follow MANRS reliagously.
3. Setting MAX PREFIX Limit
4. Configure Filters

#### RPKI
Resource Public Key Infrastructure (RPKI) authenticate BGP route announcements, currently we have 800k+ routes on the Internet, it is impossible to check them manually. RPKI is a security framework method that associates a route with an autonomous system. It uses cryptography in order to validate the information before being passed onto the routers.


#### MANRS 
Mutually Agreed Norms for Routing Security is a global initiative of network and IXP operators that provides crucial fixes to mitigate the most common threats to the Internet routing system.
It prevents basic exploits that rely on the insecurities of BGP. ISPs, Internet exchanges, cloud service providers, content delivery providers, research and education networks, and other large networks need to take action to implement MANRS guidelines for overall network security

#### Max Prefix
It automatically disables a BGP connection when a downstream network suddenly starts sending an unexpectedly large number of BGP routes, which helps in avoiding issues later.

#### Filters are MUST!

Autonomous Systems should only announce legitimate routes. Filters need to be built in order to make sure only legitimate routes are accepted. 

## Bottom Lines

Take care of your BGP's configuration, it will take care of your Network & protect resources.
Complying to MANRS and leveraging RPKI are key steps towards achieving a better network security.

