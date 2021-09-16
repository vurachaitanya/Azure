
# Azure
### Microsoft Azure Architect Technologies - Exam AZ-300
- [Acloud guru](https://learn.acloud.guru/course/5f033990-3a2e-4fe1-9d90-ecd1d0891deb/learn/1a273a93-dfb4-4306-bf40-698a6fa62658/99214cf8-4fa2-46a1-9bab-c937caa88c07/watch)

- Azure Cloud -> Subscription -> Resource group, Azure AD Tenant, Azure Tools -> 
- Azure Subscription is to create an account with Azure and create resources & resource groups inside subscription.
- Azure subscriptions are used for different subscription for different environment, LOB, Group etc.
- Resource group - contains group of resources, which give security.
- Azure AD Tenant - Outside Azure subscription. Manages accesses.
- Azure AD Tenant to use in any subscription we need to create trust between them. (Azure AD Tenant --> Trust --> Azure Subscription)
- One Subscription can't have multiple Tenant, but one Tenant can have multiple subscription.
- Management Tools:- Azure Portal, PowerShell, Azure CLI, Azure SDK. All interacts with Azure resource Manager API.

AWS | Azure
---|---
Organization| Geography
Region |Region
Availability Zones | Availability Zones
VPC across AZ| Virtual Networking across AZ
VPC | VNet
Subnet | Subnet



#### Storage Account:
- Storage name should be unique just like S3 across the Azure cloud.

- Account should be created for using Storage.
- Type of Storage
  - Container
  - Blob
  - Files
  - Queue
  - Table
  - Disk
- Catagiries 
  - Type
  - Access Tier
  - Perfomance Tier
  - Replication options

#### Network interfaces to be created( VPC)
- CIDR
- Subnet
- 

#### VM
- Create VM with Name
- Subscription --> Resource group --> VM 
- Availability zone, Image, Size of VM
- SSH port open
- HDD 
- Network - subnet, port, Network security group
- Monitoring 
- Advanced - Gen, VM Group, host Group, custom data

#### Azure Shell - CLI Bash vs PowerShell
- `az network vnet list --output table`

- [Ref](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-fundamentals/tour-of-azure-services)
## Azure Compute services :- 
- Azure Virtual Machines
- Azure Virtual Machine Scale Sets (Scaling for Windows or Linux VMs hosted in Azure)
- Azure Kubernetes Service
- Azure Service Fabric (Distributed systems platform that runs in Azure or on-premises)
- Azure Batch
- Azure Container Instances
- Azure Functions


## Networking Service :-
- Azure Virtual Network
- Azure Load Balancer
- Azure Application Gateway
- Azure VPN Gateway
- Azure DNS
- Azure Content Delivery Network (Delivers high-bandwidth content to customers globally)
- Azure DDoS Protection
- Azure Traffic Manager (Distributes network traffic across Azure regions worldwide.)
- Azure ExpressRoute(
- Connects to Azure over high-bandwidth dedicated secure connections)
- Azure Network Watcher(Monitors and diagnoses network issues by using scenario-based analysis)
- Azure Firewall
- Azure Virtual WAN (Creates a unified wide area network (WAN) that connects local and remote sites)

## Storage Services :-

- Azure Blob storage
- Azure File storage
- Azure Queue storage
- Azure Table storage

## Database Services :- 

- Azure Cosmos DB - (Globally distributed database that supports NoSQL options)
- Azure SQL Database - (Fully managed and scalable with HA)
- Azure Database for MySQL
- Azure Database for PostgreSQL
- SQL Server on Azure Virtual Machines - (Service that hosts enterprise SQL Server apps in the cloud)
- Azure Synapse Analytics - (Fully managed data warehouse with integral security at every level of scale at no extra cost)
- Azure Database Migration Service - (Service that migrates databases to the cloud with no application code changes)
- Azure Cache for Redis -(Caches frequently used and static data to reduce data and application latency)
- Azure Database for MariaDB


### Managing Organizations, resource group and resources
- Azure Management group, subscriptions, resource group, resources:
- ![Azure Arch](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-setup-guide/media/organize-resources/scope-levels.png)
- [Resources which support Regions(Resilient to the zone-wide outages) VS Non-Regional Services](https://docs.microsoft.com/en-us/azure/availability-zones/az-region#zone-resilient-services)
- **Zones VS Regions VS Region pair**
- ![Region Pairs](https://daryusman.files.wordpress.com/2019/01/5-region-pairs.png)
- Resource groups make it easy to remove a set of resources all at once.
