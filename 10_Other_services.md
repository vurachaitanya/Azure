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
