# Azure CLI

- `az network vnet list --output table` - Subnet created in the VNET(VPC)
- `az network vnet subnet create -g (Resource group)chaituRG --vnet-name vnet1 -n subnet2 --address-prefix 10.1.2.0/24` - Create new subnet
- Azure reserves 10.1.2.0,10.1.2.255 along with x.x.x.1 to x.x.x.3 from each subnets.
  
