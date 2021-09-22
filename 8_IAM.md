## IAM

#### Azure Active Director
- Controls Access
- Single Sign-on

##### AD is outside of subscription, so 1 or more subscription can be associated to AD.
- So 1 AD Tenant can have multiple subscription, but 1 subscription can have only one AD tenant. 
- Tenant can hold subscription, Device management, ID management, Roles management and Enterprise tools like Share point, Microsoft 365 etc.

##### Resources
- User Access & credentials
- Profile of user
- Security Groups
- Enterprise applications - Sharepoint/Microsoft 365
- Registered devices

##### Create new Organization/Tenant
- Home --> Create a Resource --> Marketplace --> Azre Active Directory --> Create new
- Organization - Dhani, Domain name - dhani.onmicrosoft.com, Country/region - India
- No users are there except one account which you have created.
- Tenant Vs Azure account
- Tenant should have at least one subscription.
- Account dose not required subscription.
- 
![Tenant vs subscription](https://buildcloudnext.com/wp-content/uploads/2019/07/Azure-Tenant-Directory-and-Subscription.png)

#### Key points
- All Microsoft services leverages Azure AD, including Azure, Office etc.
- Azure AD resides outside of Azure
- Azure subscription to leverage an Azure tenant should be associated to subscription.
- Azure AD has different licenses for different functionality & Availability. 
- Azure AD different from Microsoft AD and can be connected using Azure AD Connect
- Association allows identity and access to manage through **Role based access control, Single sign-on & Access Control or resources**
