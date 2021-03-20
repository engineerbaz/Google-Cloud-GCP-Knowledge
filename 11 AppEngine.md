# App Engine 
- Full managed serverless application platform
- Can scale app seamlessly with zero serer management & zero CM
- A developer can focus on more productivity and agile by supporting popular development
- Youtube & Gmail
- Famous language like PHP, Node.JS, Python, C#, .Net, Ruby & Go
- Or bring your own language runtime.

## Feature
- Popular language 
- Open & flexible
  - Custom runtime allows the user to bring any library & framework to App Engine by supplying a docker container. 
- Fully managed
- Monitoring, Logging & Diagnostics 
  - Using google stack driver
- Versioning
- Traffic Splitting
  - Route incoming request to different app versions
  - A/B testing &do incremental feature rollouts
- Application Security 
  - Help safeguard app by access rules with app engine firewall and leverage managed SSL/TLS certificates
- Service EcoSystem
- Creating CI/CD pipelines for eco
- Pay only what you use 

## App Engine Environment
- Standard
  - Like Sandbox, secure
  - Containers are preconfigured with one of several available runtimes
  - 1GB storage free 
  - Go, Java, PHP, Node.Js & Python
  - Each app in SE has an instance class, determines its compute resource & pricing

- Flexible 
  - For real based environment 
  - Container-based 
  - NO-ops part
  - Scaling possible 
  - Support microservices
  - SQL & NoSQL 
  - Supports Java 8, Python 27 & 3.6, Node.JS, Go, .Net, PHP, Ruby & Go Customised runtime.
  - its GCE VM , SSH can be used for debugging and deploying Customised Docker container.
  - Can specify amount of CPU and memory for each instance of app .


## When to choose Standard
- When sandbox 
- To deal with rapid scaling 
- optimal for app 
  - Python 3.7, Java 8
- Intended for low or free to use 
- Immediate scaling 

## When to choose Flexible
- Docker Container on GCE VMs
- Apps with consistent traffic , experience regular traffic fluctutaions, or meet the parameter for scalling up and down.
- Python, Java, .NET, Node.JS, Ruby, PHP or .NET
- Runs in Docker container that includes a Custom runtime or source code written in other programming language.
- Depends of framework  taht include native code 
- Access resources or services of GCP Projectresides in GCE network 
