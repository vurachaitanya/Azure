# Azure PowerCLI:

- `Get-AzureRMVMImagePublisher -location australisoutheast| select Publishername` - gets list of publishers name
- `Get-AzureRMVMImageOffer -Location australiasoutheast -Publisher canonical| Select Offer` - gives list of offering image type ie server/Desktop etc.
- `Get-AzureRMVMImageSku -Location australiasoutheast -Publisher canonical -Offer UbuntuServer |Select Skus` - Select version of Ubuntu, Ex 14.x,15.x,16.x,16.1.LTS
- `Get-AzureRMVMImage -Location australiasoutheast -Publisher canonical -Offer UbuntuServer -Sku 16.04-lts |Select Version` - List all version in 16.x image Ex: 16.04.201703270, 16..04.201703280 etc.
- User this in power shell to set the Latest image: `Get-AzureRmVMSourceImage -Publishername Canonical -Offer UbuntuServer -Skue 16.04-LTS -Version latest`
- `sudo waagent -deprovision+user -force` [Linux image to generalised](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/capture-image) - removes users which are not generic to make image out of the VM Linux OS.
- Azure reserves x.x.x.0,x.x.x.255 along with x.x.x.1 to x.x.x.3 from each subnets.
- `New-AzureRmStorageAccount -ResourceGroupName chaitu_rg -AccessTier Hot -SkuName Standard_GRS -Kind BlobStorage -AccountName Storageaccount1 -Location US East `  - Create Storage Account. 
  


### Azure CLI:

- Az login setup
- need to place Azure certs under below pem file and update below date in /etc/profile file.
```
#alias tf="terraform init && terraform plan && terraform apply -auto-approve"
alias tf="terraform init && terraform apply -auto-approve"
#alias tf="terraform apply -auto-approve"
alias lab="cd /home/chaitu/Desktop/code/learning"
alias listtf="find . -type d -name .terraform -exec du -sh {} \;"
alias removetf="find . -type d -name .terraform -exec rm -rf {} \;"
#export TF_LOG=DEBUG


export REQUESTS_CA_BUNDLE=$HOME/certs/az-cli-extra-certs.pem
AZURE_CLI_DISABLE_CONNECTION_VERIFICATION=1
```

- Azure Cli install on windows/Linux
- [List Azure Resources created in JSON format. API Calls can be listed](https://resources.azure.com/)
- Azure cloud Shell
  - For using Cloudshell you need to create Storage account and subscription
  - `az storage account list --query [].name` - list the storage account name using JQ Query.
- `/etc/apt/sources.list.d/azure-cli.list` - Source repo should be updated with Azure example : `deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ bionic main`
- `sudo apt-get install azure-cli` Install Azure cli on ubuntu [Doc](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt)
- `az login` - Login to Azure cloud
- `az find secret` - search for command names containing secret
- `az login --use-device-code` or `az login -u <username> -p <password>` - If no web browser is available or the web browser fails to open
- `az --version` - Check to see always to be on latest version.
- `az vm --help|more` - Help command
- `az  vm create --help` - Help command with examples
- `az login -o table` - to view in table format.
- `az account list -o table` - list of all the subscriptions for your Azure account 
- `az account set subscription --subscription 'your_subscription_name'` - change the default subscription
- `az resource list -o table` - List Resources
- `az interactive` - **interactive shell installed by default but Azure CLI**
- `az configure` - configure the table format to be your default standard output
- `az upgrade` - upgrade your Azure CLI 
- Command to create a VM :
```
az vm create \
  --image UbuntuLTS \
  --admin-username user1 \
  --ssh-key-value ~/.ssh/id_rsa.pub \
  --resource-group RG1 \
  --location canadaeast \
  --name Ubuntu1
``` 

### Azure Network:
- `az network vnet list --output table` - Subnet created in the VNET(VPC)
- `az network vnet subnet create -g (Resource group)chaituRG --vnet-name vnet1 -n subnet2 --address-prefix 10.1.2.0/24` - Create new subnet
- `az network nic create -g chaituRG --vnet-name chaituVnet --subnet chaituSubnet1 -n chaituNic1` - Create new NIC 
- `az network vnet subnet update -g chaitu_rg --vnet-name vnet1 -n subnet1 --service-edpoints "Microsoft.Storage"` - Create Service Endpoints
