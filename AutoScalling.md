# AutoScaling

For regions that contains more than 3 zone that regional managed instance group willl choose 3 zone to create instance in 

## Instance template
- Machine Type, Boot disk image or container image, zone, labels and instance properties
- Managed instance group allows autoscalling by adding & removing instance based on increase or decrease

## Creating Instance Template
- Name for instance template
- Machine Type
- Start-up Script
- Networking details to include the network in which the instance will spin up 
- SSH keys 

### Trigger 
- CPU usuage 
- stackdriver monitoring metric 
- Multiple metric
 Autoscaler is created by specifying the autoscalling
 
### Option
Canary upgrade,rolling restart & replace
- REPLACE = Delete existing & create new one with target template
- RESTART = Perform stop & Start instance
- CANARY UPGRADE = use different template with different condition or set parameter


### Rolling Update
- Max Surge = 
  - Temporary Allowable value of instance above your required values
  - If work with Max instance number or % if instance group has 10 or more than that
  - OverProvison
- MaxUnavailable
  - number of unavailable instance 
  - no additional cost 

### Estimated 
- CE recommends that provision enough instances, if all of the instances in any one zone are unavailable
- recommended additional VMs is inversly propational to the number of zone where your managed IG is located.
| number of Zones | additional VM | recommended VMs |
| 2 | +100% | 200% |
| 3 | +50% | 150% |
| 4 | +33% | 133% |
