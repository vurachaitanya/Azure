# Azure CLI

- `az network vnet list --output table` - Subnet created in the VNET(VPC)
- `az network vnet subnet create -g (Resource group)chaituRG --vnet-name vnet1 -n subnet2 --address-prefix 10.1.2.0/24` - Create new subnet
- `az network nic create -g chaituRG --vnet-name chaituVnet --subnet chaituSubnet1 -n chaituNic1` - Create new NIC 
- Azure reserves x.x.x.0,x.x.x.255 along with x.x.x.1 to x.x.x.3 from each subnets.
  
