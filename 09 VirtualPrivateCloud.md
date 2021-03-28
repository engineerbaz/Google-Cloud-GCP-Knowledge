# VPC
- Virtual Privaet Cloud
- Managing Networking functionality for cloud platform
- Private space within GCP
- Flexibility  to control how workload connect regionally or on-prem
- Provides connectivity for VM, K8s, app engine, flex instance, and other resources
- VPC is free (including RT, Subnet, etc)
- VPC Global
  - A single Google VPC can span multiple regions without communicating across the public internet
  - For on-prem scenarios, you can share a connection between VC and on-prem with all-region in a single VPC

## VPC Shareable 
With Single 
## VPC Expandable 
- Withouut shutdown or downtime addition IP Space 
- NO option in other CSP 
## Private VPC 
Service like (IoT, AI) to communicate 
## VPC Transparent
- Like AWS Flow log
- 5 second interval 

## FEature
- Cloud Router
  - For Dynamic routing, CR is required for BGP, VPN
- VPN
  - Over IPSec
- Firewall
  - Global restricted Firewall
  - Tag based
- VPC Peering
  - When private communication the same or different organization without BW or SPOF
- Shared VPC
  - Shared across several organization 
- Routes
- VPN Flow Log

## Uses of VPC
- Multi tier application
- Connecting GCP hosted or externally hosted Database 
- DR

## VPC Pricing
- Ingress & Egress
- VPN
- IP address 
- Networking telemetry 



