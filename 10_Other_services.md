### Azure DSC :
- Azure Desired State Configuration extension handler - extend VM functionality and simplify various VM management operations.
- Bootstrap a VM (Windows) to the Azure Automation State Configuration (DSC) service.

### Azure Resource Locks :
- You can lock a subscription, resource group, or resource to prevent other users in your organization from accidentally deleting or modifying critical resources. The lock overrides any permissions the user might have.
- lock level 
  - CanNotDelete :  authorized users can still read and modify a resource, but they can't delete the resource.
  - ReadOnly : authorized users can read a resource, but they can't delete or update the resource. Applying this lock is similar to restricting all authorized users to the permissions granted by the Reader role.
- [Azure Doc](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources?tabs=json)
- [Youtube video](https://www.youtube.com/watch?v=d374K0qVZdA)

### VNet-to-VNet :
- [Azure Doc](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-vnet-vnet-resource-manager-portal)
- Virtual networks can be in different regions and from different subscriptions. When you connect VNets from different subscriptions, the subscriptions don't need to be associated with the same Active Directory tenant. This type of configuration creates a connection between two virtual network gateways.
- When you connect a virtual network to another virtual network with a VNet-to-VNet connection type (VNet2VNet), it's similar to creating a Site-to-Site IPsec connection to an on-premises location. Both connection types use a VPN gateway to provide a secure tunnel with IPsec/IKE and function the same way when communicating.


### Azure Backup : [MS Ref](https://docs.microsoft.com/en-us/azure/backup/backup-azure-arm-vms-prepare#before-you-start)
- Backup center will take database, VM, application backup
- Can scheduled based on requirement 
- Retention is given to store the old snapshots
- Automatic deletion of old after n no.of days.
- Dashboard metrics for backup status can be viewed
- Disk Metrics can be viewed
