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

### Alerts and Action Groups :
- Azure Monitoring -> Alerts 
- Alerts are features of Azure Monitoring to perform some action against to the log or metric of an resource. 
- Alert rule created with action group to trigger based on condition for a given resource.
- Alerts status:
  - New
  - Acknowledged 
  - Closed
- Historical info about the alert states and monitor condition are recorded.
- Alert groups are used with in alerts to define what should happen when alert triggered like emails, sms, voice, calling Azure Functions and many more.
- [Action group limits ](https://docs.microsoft.com/en-us/azure/azure-monitor/service-limits#action-groups)
- Rate limit thresholds :
  - SMS : Not more than 1 SMS every 5 Min
  - Voice : Not more  than 1 Voice call every 5 Min
  - Email: No more than 100 emails in an hour
