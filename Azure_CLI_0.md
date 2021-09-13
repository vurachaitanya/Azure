# Azure CLI

- `az network vnet list --output table` - Subnet created in the VNET(VPC)
- `az network vnet subnet create -g (Resource group)chaituRG --vnet-name vnet1 -n subnet2 --address-prefix 10.1.2.0/24` - Create new subnet
- `az network nic create -g chaituRG --vnet-name chaituVnet --subnet chaituSubnet1 -n chaituNic1` - Create new NIC 
- `Get-AzureRMVMImagePublisher -location australisoutheast| select Publishername` - gets list of publishers name
- `Get-AzureRMVMImageOffer -Location australiasoutheast -Publisher canonical| Select Offer` - gives list of offering image type ie server/Desktop etc.
- `Get-AzureRMVMImageSku -Location australiasoutheast -Publisher canonical -Offer UbuntuServer |Select Skus` - Select version of Ubuntu, Ex 14.x,15.x,16.x,16.1.LTS
- `Get-AzureRMVMImage -Location australiasoutheast -Publisher canonical -Offer UbuntuServer -Sku 16.04-lts |Select Version` - List all version in 16.x image Ex: 16.04.201703270, 16..04.201703280 etc.
- User this in power shell to set the Latest image: `Get-AzureRmVMSourceImage -Publishername Canonical -Offer UbuntuServer -Skue 16.04-LTS -Version latest`
- `sudo waagent -deprovision+user -force` [Linux image to generalised](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/capture-image) - removes users which are not generic to make image out of the VM Linux OS.
- Azure reserves x.x.x.0,x.x.x.255 along with x.x.x.1 to x.x.x.3 from each subnets.
  
