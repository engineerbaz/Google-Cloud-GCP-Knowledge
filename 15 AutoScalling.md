# AutoScaling
- ASG in GCP is a feature of the managed instance group.
- A managed instance group is a pool of homogenous instance, created from a common instance template.
- For regions that contains more than 3 zone that regional managed instance group willl choose 3 zone to create instance in. (supported where IPAM policy is specified)
- ASG can be created for both single zone ( with multi zone support) and multiple zone (regional)

## Instance template
- An instance template is an API resource taht can use to create VM instance and managed IG 
- Machine Type, Boot disk image or container image, zone, labels and instance properties
- user can use an instance template to create a managed IG or to create individual VM instance
- Managed instance group allows autoscalling by adding & removing instance based on increase or decrease

## Creating Instance Group
- Name for instance group
- Region, Location, Choice of region as per user
- Instance template
- AutoScaling Option
- Choosing CPU as the option and the target CPU usuage
- Max and Min instances to spin up using IT 
- cool down period (period after which the instance boots up and the information is collected)
- Health Check for autohealing
- Delay

## Creating Instance Template
- Name of instance Template
- Machine Type
- Start-up Script
- Networking details to include the network in which the instance will spin up 
- SSH keys (optional)
- IP forwarding (enabled ON)


### Trigger in Instance Template
- CPU usuage 
- stackdriver monitoring metric 
- Multiple metric
 Autoscaler is created by specifying the autoscalling policy and a target utilization level.
 
### Option
Canary upgrade,rolling restart & replace
- REPLACE = Delete existing & create new one with target template
- RESTART = Perform stop & Start instance
- CANARY UPGRADE = use different template with different condition or set parameter, Ensure network selected as that of the IG 

### Rolling Update
- Max Surge = 
  - Temporary Allowable value of instance above your required values
  - If work with Max instance number or % if instance group has 10 or more than that
  - OverProvison
  - This option is only used with REPLACE
- MaxUnavailable
  - number of unavailable instance 
  - no additional cost 
  - If work with Max instance number or % if instance group has 10 or more than that

### Estimating the recommended instance group size
- CE recommends that provision enough instances, if all of the instances in any one zone are unavailable
- recommended additional VMs is inversly propational to the number of zone where your managed IG is located.

| number of Zones | additional VM | recommended VMs |
| :-------------- | :------------ | :-------------- |
| 2               | +100%         | 200%            |
| 3               | +50%          | 150%            |
| 4               | +33%          | 133%            |

### Limitation
- Not more than 1000 instances
- Only created under Project ID 


---