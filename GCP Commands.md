GCP command-line cheatsheet
Daniel Weibel
Daniel Weibel
Follow
Nov 19, 2019 · 4 min read





A cheatsheet with various commands for the Google Cloud Platform (GCP) command-line tool (gcloud).
I plan to extend this list further as I encounter more commands.

Table of contents
Create a new project and set it as the default
Set a default project
Set a default compute region and zone
Disable interactive prompts
List the current CLI configuration
Create a VPC network with custom subnets
Create a VPC network with automatic subnets
Get all subnets of a VPC network
Create a compute instance with a specific machine type
Create a compute instance in a specific VPC network and subnet
Create a compute instance with a specific OS image
Get the VPC network and subnet of a compute instance
Get the names of all compute instances
Allow ingress traffic to a VPC network
Create a regional static IP address
Create a global static IP address
Create a new project and set it as the default
gcloud projects create black-butterfly-4450 \
  --name black-butterfly \
  --set-as-default
black-butterfly-4450 is the project ID (must be globally unique)
black-butterfly is the project name (must be unique in your account)
If --name is omitted, the project name is set equal to the project ID.
Set a default project
gcloud config set core/project black-butterfly-4450
You must specify the project ID (globally unique) not the project name.
👉 Config settings 👈
Set a default compute region and zone
gcloud config set compute/region europe-west6
gcloud config set compute/zone europe-west6-a
👉 Regions and zones 👈
Disable interactive prompts
gcloud config set core/disable_prompts 1
Disables all interactive prompts, for example, when deleting resources.
Alternatively, you can set the CLOUDSDK_CORE_DISABLE_PROMPTS=1 environment variable or use the -q/--quiet global with individual commands.
List the current CLI configuration
gcloud config list
Create a VPC network with custom subnets
Create VPC network without any subnets:
gcloud compute networks create my-vpc --subnet-mode custom
A VPC network is is global. Subnets are regional.
2. Manually create a subnet:
gcloud compute networks subnets create my-subnet-1 \
  --network my-vpc \
  --range 10.240.0.0/24
Create a VPC network with automatic subnets
gcloud compute networks create my-vpc
Automatically creates a subnet in every region.
Subnets have a */20 CIDR range (e.g. 10.128.0.0/20).
Get all subnets of a VPC network
gcloud compute networks subnets list --filter="network:my-vpc"
👉 Filter syntax 👈
Create a compute instance with a specific machine type
gcloud compute instances create i1 --machine-type=n1-standard-2
👉 Machine types 👈
Default machine type is n1-standard-1 (1 CPU, 3.75 GB RAM)
Instance name argument can be repeated to create multiple instances
Create a compute instance in a specific VPC network and subnet
gcloud compute instances create i1 \
  --network my-vpc \
  --subnet my-subnet-1
Default VPC network is default
If --network is set to a VPC network with “custom” subnet mode, then --subnet must also be specified
Instance name argument can be repeated to create multiple instances
Create a compute instance with a specific OS image
gcloud compute instances create i1 \
  --image-family ubuntu-1804-lts \
  --image-project ubuntu-os-cloud
👉 Images 👈
Default image family is debian-9
User either --image-family (uses latest image of this family) or --image (a concrete image)
--image-project serves as a namespace for --image and --image-family(may have multiple images/image families with same name in multiple projects)
List all available images (including projects and families) with:
gcloud compute images list
Get the VPC network and subnet of a compute instance
{
  gcloud compute instances describe i1 \
    --format "value(networkInterfaces.network)" |
    sed 's|.*/||'
  gcloud compute instances describe i1 \
    --format "value(networkInterfaces.subnetwork)" |
    sed 's|.*/||'
}
👉 Format syntax 👈
Get the names of all compute instances
gcloud compute instances list --format="value(name)"
👉 Format syntax 👈
Can be used, for example, for deleting all existing compute instances:
gcloud compute instances delete \
  $(gcloud compute instances list --format="value(name)")
Allow ingress traffic to a VPC network
gcloud compute firewall-rules create my-vpc-allow-ssh-icmp \
  --network my-vpc \  
  --allow tcp:22,icmp \
  --source-ranges 0.0.0.0/0
0.0.0.0/0 is the default for --source-ranges and could be omitted.
This allows incoming ICMP and SSH (TCP port 22) traffic to any instances in the VPC network from any source (e.g. from the public Internet).
After creating this firewall rule, you’re able to:
Ping instances in the VPC network: ping EXTERNAL_IP
SSH to instances in the VPC network: gcloud compute ssh i1
Note that a newly created VPC network has no firewall rules applied and instances cannot be reached at all (not even from inside the VPC network). You have to create firewall rules to make compute instances reachable.
Create a regional static IP address
gcloud compute addresses create addr-1 --region=europe-west6
Regional IP addresses an be attached to compute instances, regional load balancers, etc. in the same region as the IP address.
The name argument can be repeated to create multiple addresses
One of --global or --region must be specified.
Create a global static IP address
gcloud compute addresses create addr-1 --global
Global IP addresses can only be attached to global HTTPS, SSL proxy, and TCP proxy load balancers.
The name argument can be repeated to create multiple addresses
One of --global or --region must be specified.
Google Cloud Platform
Cloud
Command Line
Cheatsheet