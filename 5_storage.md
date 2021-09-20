### Storage Account :

![Storage types](https://azuretrainings.files.wordpress.com/2019/06/storageaccountkinds.jpg)

#### Types of SA
- Blob Storage
- General purpose
- General purpose V2 - Recommended 

##### Blob Storage:
- Supports for block and append blobs.
- Legacy, used before GP V2 for access tiers.

##### General purpose V1:
- All storage services.
- Low in transaction prices, but higher storage price.
- Support classic Azure Service manager

##### General purpose V2: - Recommended by Azure
- All Storage services + latest features. 
- Supports access Tiers like Cool and Archive storage.
- Supports Zone redundant storage

![Storage Account types](https://www.edureka.co/community/?qa=blob&qa_blobid=12800761455423777756)


- PowerSheel command to create storage account:
```
New-AzureRmStorageAccount -ResourceGroupName chaitu_rg
-AccessTier Hot `
-SkuName Standard_GRS `
-Kind BlobStorage `
-AccountName Storageaccount1 `
-Location US East `
```
### Storage Account - Performance Tiers
##### Two performance Tiers
- Standard : Magnetic drives and Low cost. Supports by all Storage account, storage services. 
- Premium : SSD, High performance and low latency access. 
- Premium performance Only used with VM disk. ex High I/O Ops like DB servers etc.
- give 99.% SLA, uptime

Standard | Premium
---|---
Magnetic drives & Low cost|SSD, High Performance
Low latency|High latency
Geo redundant storage|Locally redundant
All storage Tiers| General purpose type SA
Major resource |VM Only
NA | 99.9% SLA

### Storage Account - Access Tier
###### 3 Access Tier, Only for Blob storage

Storage tier type|Description
---|---
Hot storage| Frequently access data
Cool storage| Infrequently access data at least 30 days old
Archive Storage| Rarely access data more than 180 days

- Based on frequently read and write
- We can change the tier based on requirement but price will varies. 
- Configured at SA but set at object level too.
- Archive level is set at Oject level.
- General purpose V1 will not support.

### Storage Account - Replication options
##### 4 types of replication options for data replication.

- LRS - Local redundant storage - Replicates to another storage scale unit 
- ZRS - Zone redundant storage - Across the zones, with in storage cluster with single region. All regions are not supported.
- GRS - Geo redundant storage - Replicates across regions
- RA-GRS - Read access to across GRS - Read from secondary copy

##### Synchronization :
- LRS & ZRS replication occurs syn.
- GRS and RA-GRS replicates Asyn.
