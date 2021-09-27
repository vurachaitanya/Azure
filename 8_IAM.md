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

### Device registration
- Bring your own device - Register, Trusted, Secure access
### 3 ways of registration a device
- Azure AD registered - BYOD, Provides identity, Access to Organization resources
- Azure AD join  - Org Own devices but not part of Org AD, Change local state to get more control and provide SSO to Azure managed resources.
- Hybrid Azure AD joined - Org added to on-prem AD, supports SSO and ESR(Enterprise State Roam).

### ESR (Enterprise State Roam)
- Sync user data across the devices.
- Settings stored in cloud
- **Azure AD --> Devices --> Enterprise State Roam**
- Retains data after 90 to 180 days after deleting user profile


### Self Service Password reset
- Its Azure AD feature for end users ability to reset the own password
- Azure AD --> Password Reset, Properties --> Configure SSPR to All - to allow all
- Registered users are only allow to use this feature
- https://aks.ms/ssprsetup for registration
- Reset portal https://aks.ms/sspr 

##### Authentication methods
- Password
- security questions
- Email address
- MS Authenticator app
- OATH Hard token
- SMS or Voice

### Azure AD Identity protection :
- Azure Active Directory Identity protection is the service provided by Microsoft. 
- Detects Anomalies and suspicious incidents related to Identity.

##### Dependencies :
- Azure AD Premium P2 Liciensing
- Create resource Azure AD Identity protection as new resource.

###### Types of Policies 
- Multi factor authentication - Granular control
- Block risk user account - Risk level to enforce password reset
- Sign-in risk policy - real time, Risk level from MFA, Can apply to modern auth traffic.
![Risks](https://docs.microsoft.com/en-us/azure/security/fundamentals/media/steps-secure-identity/azure-ad-sec-steps3.png)
- Azure AD Identity protection evaluates your env for vulnerabilities

### Azure  Multi Factor Authentication
- Requires additional infra to manage.
  - MFA Server -our own
  - Cloud base MFA
- MFA Can be enabled 2 ways
  - From Azure portal
  - From Identity protection 
- Range of ways to authenticate
  - Call
  - Text
  - Mobile app
  - Hardware token vs app
- Bypass MFS
  - From Conditional Access policy
  - One time for certain amount of time.
  - Trusted IP

### Azure AD Access Conditions
- Conditions based on locations / IP (Portal -> Dashboard -> Linux Academy Azure --> Conditional Access Terms of use)
- Conditional access Policies  based on location, Group, User, All, applications, Devices etc.
- [More details](https://lucid.app/lucidchart/8fd7f8ce-ddfa-405a-a46a-2551195187c8/view?page=Le_O0Vtf-_pP#)
- [Azure Video](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)


### Role Based actions:
- [RBAC](https://lucid.app/lucidchart/8fd7f8ce-ddfa-405a-a46a-2551195187c8/view?page=Le_O0Vtf-_pP#)
- [List of Built in Roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)

- `az role definition create --role-definition ./customRole.json` - Command to create a role.
```
{  
  "Name": "LAAzureAdmin",
  "IsCustom": true,
  "Description": "Read access to Network, all access to Compute, Storage & Support"
  "Actions": [
    "Microsoft.Compute/*",
	"Microsoft.Storage/*",
	"Microsoft.Support/*",
	"Microsoft.Network/*/read",
   ],
   "NotActions": [],
   "AssignableScopes": [
      "/subscriptions/xxxxx"
	]
}
```

#### Hybrid Identities :
- [Details](https://lucid.app/lucidchart/8fd7f8ce-ddfa-405a-a46a-2551195187c8/view?page=7d_Owad0QYIk#)
- If we have Hybrid cloud (datacenter + Cloud) AD then we can configure in:
  - Onprem Datacenter accounts to recreated in Cloud AD
  - Sync the Onprem AD to Cloud AD
  - Hybrid Identities which can Sync bi- direction ie from Onprem to Cloud and Cloud to Onprem.
- In Hybrid Identities we have 3 ways:
  - **ADFS** : Federation - Auth -> Onprem -> Azure cloud
  - **PHS** : Password Hash Sync - Only Password Hash is syncted to cloud
  - **PTA** : Pass thought Authentication - Auth happens OnPrem, Best of all, Secured, but Agent is required, MFA not supported, Can't sync multiple servers so staging is required. 
  - **Seamless SSO** : supported by PTA or PHS only, don't need to give the password multiple times.
  
### Azure AD Connect:
- Azure AD Connect pkg should be installed in Onprem server, not part of Azure Cloud. 
- **Password Hash Sync - PHS** : 
- Once created need to sync to the to using the Agent to Stand by server and exports to the Azure AD server
