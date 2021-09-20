## Azure Monitoring
- Azure has created Azure monitoring services and placed all services related to logging and monitoring in one section.
![Azure Monitoring](https://docs.microsoft.com/en-us/azure/azure-monitor/media/overview/overview.png)

#### Azure captures from :
- Tenants
- Subscription
- Application
- Resources
- Guest OS

#### Azure captures :
- Logs
- Metrics 

#### Azure Metrics:
- Metric information of the resources like (CPU, Memory, Network etc) based on time.

#### Azure Logs:
##### Diagnostic logs
- Types of Diagnostic logs :
 - Tenant Logs : Outside of an Azure Subscription
 - Resources Logs : Resources  deployed with in Azure subscription.
 - OS level logs : Agent running in a VM.
- Can create logs for all the resources with minimal configuration.
- Can be created from Azure Monitoring 
- Need to install Agents to the resources. Using VM Extensions we can install agent inside a VM.
 
##### Log storage :
- SA for archival
- Log Analytics for search and analytics.
- Event hub to integrate with other solutions.


##### Activity logs :
- Subscription level logs for write operation (put,Post,Delete), but not the Read operation (Get)

##### Source of Activity logs
- Administrative : Create, Update & delete activities done from Azure resource manager.
- Service Health
- Resource Heath (Available, degraded, Unknown)
- Alert
- Auto scale
- Security - From Azure Security Center.
- Policy


