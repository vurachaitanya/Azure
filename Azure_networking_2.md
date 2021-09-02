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
