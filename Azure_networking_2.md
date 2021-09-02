# Azure Networking

### AWS VPC vs Azure VNet :
![Vnet vs VPC](https://github.com/vurachaitanya/Azure/blob/main/images/AWS%20VPC%20vs%20Azure%20Virtual%20Net(VNet).jpeg)
###### [image used from](https://medium.com/awesome-azure/azure-vs-aws-difference-between-azure-virtual-network-vnet-and-aws-virtual-private-cloud-vpc-2e8debc3290e)

### Virtual Network

### Subnet
- Azure reserves x.x.x.0, x.x.x.255 along with x.x.x.1 to x.x.x.3 from each subnets.
- We should be creating Public and Private subnet.
- 


### Nic - Network Interface Card
- Used for Connect virtual machines for participating in the networking. 
- Independent resources.
- It can be attached to Public or Private subnets.
- It can have single or multiple ip address.
- Command to create NIC `az network nic create -g chaituRG --vnet-name chaituVnet --subnet chaituSubnet1 -n chaituNic1`
- IP Forwarding, accelerated networking are disabled by default
- IP attached using DHCP
- It should be part of one Subnet group.
- DNS can be set to it.
- View or update network security group.

### Private vs Public
- **Private IP** : are used to communicate locally within Azure virtual network and with On prem network when using a VPN or Route connection.
- **Public IP** : Used when resources connection over Internet.
#### Key features of Public IP :
- Independent resources 
- Can be connected to VM's or VPN Gateways.
- When we choose Public + dynamic, ip address will not be assigned unless it is been attached to any resources. 
- Can have 2 SKU - Basic & Standard.
##### Basic SKU : 
- Supports Static or dynamic allocation  of IP's
- Can attach any resources which supports public IP
- No Security rules applied, so open ports for these IP's.

##### Standard SKU :
- supports Static allocation only.
- Can assigned to NIC, Public LB, Application Gateways and VPN Gateways.
- Default deny Rule and requires Network security groups to explicitly allow.
- Supports HA by Zone redundancy.
- POWERCLI `get-azurermnetworkinterface -resourcegroupname chaituRM -name chaituNic1`
  
