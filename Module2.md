# Module 2 - Azure Core Services

## Geographies - Help to contain datacentre areas (regions)

Categorised

- Americas
- Europe
- Asia pacific
- Middle East
- Africa

### Regions

- Region - collection of datacentres
- Provide flexibility and scale
- Some regions have different resources - newer hardware etc
- Some regions cost different amounts
- Choose region closest to users
- Regions have specific compliance
- Every region has a pair, failover to a different datacentre if there is an error - user doesn't choose
  - Don't update both pairs at the same time incase there is an error
  - Pair has to be inside the same geography
- May be multiple data centres within one facility

## Availability zones and sets

- For 2 VMs or more so for IaaS
- Mutually exclusive
- Protect against updates or faults
- No cost
- When setting up a VM, must put in same region as zone/set

### Availability zones

- Physically separate locations in a region
- Separate maintenance systems
  - Power
  - Cooling
  - Networking
- 3 availability zones in every region
- Recommended option
- 99.99% SLA

### Availability sets

- Older concepts
- Multiple racks in one datacentre
- Fault domain - Separation of workloads across different hardware
- Update domain - Scheduled maintenance etc at different times
- 99.95% SLA

### Single server SLA

- 99.9% SLA for one VM
- Must use premium storage

## Resource group

- Container that has all resources in
- Used to have the same lifecycle for application
- Single management unit
- Often talk to each other
- Contain resources from multiple regions
- Contain different types of resources
- If you delete a resource group, all the resources in the group are deleted

## Azure hierarchy

1. Management groups
2. Subscriptions
3. Resource groups
4. Resources

Tenant - Where the Azure AD is, you log onto the tenant in order to access the subscriptions

## Preview

While in preview there is no SLA, so don't deploy to production

## Setup

### Disks

Using a managed disk gives better prediction on the cost

### Logs

Logs can be used to get greater detail as to the consumption of resources

### Templates

When setting up a VM, you can save the template to easily create another of the same config in the future

### Bastion

Put VM in public network that requires authentication to ensure security

## Virtual machine services

- VMs
- VM Scale sets - scale out and in automatically
- App services (PaaS)
- Functions (PaaS)

## Containers

- One OS for multiple containers
- Container runtime for all to adhere to
- Makes application more movable and portable
- Faster and more efficient

### Kubernetes

Container orchestrator service for managing large numbers of containers

## Azure network services

- Azure Virtual Network
- Azure Load Balancer
- VPN gateway
- Azure application Gateway - Inspect traffic to ensure valid packets
- CDN

### Peering

- Connecting virtual networks together inside of Azure
- Doesn't encrypt traffic - Need VPN Vnet for additional security
- Already inside of Azure so encryption isn't compulsory here

### Point to site connection

- Admin point into azure virtual network
- Max speed 100Mbit

### Site to site connection

- Connect office environment to azure
- Default speed 100Mbit, up to 1Gbit

### ExpressRoute

- Private dedicated connection to Azure, not running over public internet
- Can be expensive
- 1Gbit to 10Gbit
- Need to pay extra to run a fibre connection

## Data

### Structured Data

- SQL server etc with schema

### Semi-structured data

- JSON etc

### Unstructured data

- Most common
- Blob storage

### Storage account

- Both IaaS and PaaS
- IaaS
  - Disk services
- PaaS
  - Containers for Blobs
  - Tables for NoSQL etc
  - Queues for messages, applications communicating with each other

Server message block - Allowing access to files in the cloud, can only access with files

Access Tier:

- Hot storage - Fast to access
- Cool storage - Latency to access

Need globally unique name for storage name - accessing `name.blob.core.windows.net` etc.

#### Replication

- Zone Redundant storage - Like availability zones
- Geo Redundant Storage - Store in peer region
- Read Access Geo Redundant Storage - People close to the peer region can read the data

#### Security

Secure transfer required allows for encryption in transit as well as at rest

## Azure Database

- Azure cosmos DB - NoSQL
- Azure SQL DB - PaaS service
- Azure Database Migration - Move data from on premises and other cloud providers

## Azure Marketplace

- Buy solutions from Microsoft Partners

## IoT

- Microsoft IoT central
- Microsoft IoT hub - bidirectional data transmission

## Big Data

- Azure synapse analytics - parallel processing
- Azure HDInsignt - Pulling information from data
- Data lake analytics - On demand analytics job service

## AI

- Azure Machine Learning service - for data scientists
- Azure machine learning studio
  - No need to write code
  - Drag and drop

## Serverless Computing

- Azure functions - One event comes in, one event comes out. Based on an event
- Azure logic apps - Need to make decision based on event coming in
- Azure event grid - Want to do multiple things based on the information that is coming in

## DevOps

- Kanban boards
- Git repos
- Load testing
- Pipelines

DevTest labs:

- Quickly create environments
- Controlling costs

## Azure app service

- Quickly and easily build web and mobile apps for any platform or device
- PaaS

## Azure Management Tools

- Authenticate against Azure resource manager
- Azure powershell allows local systems to communicate with Azure
- Azure CLI runs on top of Bash or Powershell
- Cloud shell within portal
- Azure Mobile app - Features cloud shell

`az` to run azure commands in cloud shell

`az [command] --help` for man pages

powershell `get-help` is equivalent of man pages
