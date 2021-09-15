
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


## Azure Compute services:- 
- Azure Virtual Machines
- Azure Virtual Machine Scale Sets (Scaling for Windows or Linux VMs hosted in Azure)
- Azure Kubernetes Service
- Azure Service Fabric (Distributed systems platform that runs in Azure or on-premises)
- Azure Batch
- Azure Container Instances
- Azure Functions
