### VM Images:
- Azure has created Market place for different images for different providers & Custom images where user defined images present.
- We can upload our own images to Custom images or customize images which are already there in market place.
- Image are used to build the VM's OS disk.
- We can't install OS from the console. Hence pre deployed & pre configured Images are preset to directly consume them.
- We can convert VM OS which is configured as per our requirement to an image, so as to make multiple VM's.
- **Market place images** will have following parameters:
  - Publisher : Organization
  - Offer : OS/type ex: ubuntu/Server
  - SKU : an instance of the offer ex: 16.0.4-LTS, 2016-data center
  - version: version of SKU, Ex: 16.0.4.1, Latest - can be used to get the latest version.
- `Get-AzureRMVMImagePublisher -location australisoutheast| select Publishername` - gets list of publishers name
- `Get-AzureRMVMImageOffer -Location australiasoutheast -Publisher canonical| Select Offer` - gives list of offering image type ie server/Desktop etc.
- `Get-AzureRMVMImageSku -Location australiasoutheast -Publisher canonical -Offer UbuntuServer |Select Skus` - Select version of Ubuntu, Ex 14.x,15.x,16.x,16.1.LTS
-  `Get-AzureRMVMImage -Location australiasoutheast -Publisher canonical -Offer UbuntuServer -Sku 16.04-lts |Select Version` - List all version in 16.x image Ex: 16.04.201703270, 16..04.201703280 etc.
- User this in power shell to set the Latest image: `Get-AzureRmVMSourceImage -Publishername Canonical -Offer UbuntuServer -Skue 16.04-LTS -Version latest`
- **VM to Image Conversion :** 
  - Go to VM
  - click on Capture
  - Generalize the VM so that user name/Password don't need to be carry across all VM's.
  - Windows tool has sysprep.exe 
  - Linux `sudo waagent -deprovision+user -force` [Linux image to generalised](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/capture-image) - removes users which are not generic to make image out of the VM Linux OS.
  - Deallocate the VM (shutdown the VM)
  - Mark the vm as generalize 
  - Create an image from the VM.
  - Any VM convereted to image, can't be used. 
  
### VM Storage:
- 3 Type of disk :
  - OS Disk - OS files
  - Data disk - created as blank disk
  - Temporary disk - Includes with all VM - Data can be lost after reboot.
- VHD - Virtual Hard disk, are source to create disk or images.
- VM disk can be managed or unmanaged 
  - Unmanaged :- manual config storage account. Belongs to VM.
  - Managed :- Need Storage account but Azure take care of reliability, performance. These are independent resources
- VM disks performance tiers :
  - Standard HDD : Cost effective, Low IOPS
  - Standard SDD : Good consistency and reliability.
  - Premium SDD : High performance, Low latency, S name while accessing to VM.
- **Azure storage service encryption** at infra level, disk stealing which will not give access to the data.
- **Azure Data Encryption** - protects the data one login in to you account, VM is on. Can't transfer or export the data. 
- [List Azure Resources created in JSON format. API Calls can be listed](https://resources.azure.com/)

### Virtual Machine Extensions :
- Different type of extensions can be installed to extract required data from VM, example custom script, symantec endpoint, datadog etc.
- VM Extensions are lightweight application or services which assist post deployment configuration or various automation tasks on VMs.
- Custom script to run by setting language setting, timezone etc.
- **Azure Diagnostics extension** to support additional monitoring. 


### VM Network
- NIC care independent resource and can attach to VM
- NIC are created in VNet in a subnet.
- VM is configured to forward packets, then **IP Forwarding must be enabled on NIC too**.
- Static IP is not recommended for private IP configured on OS of a VM.
- IF VM is using multiple IP's then static configuration is required to configured at OS.
- For NIC you should set DNS inherited from VNet, but you can use custom also.


