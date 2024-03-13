# Identity

## Basics
- For any service it is critical to be apply principle of least privilege
- Use roles and scopes vs shared accounts
- IDP - responsible for storing credentials and acting as a central hub for identities. Acts as a glue between your Apps/Services and your Directory/User mgmt platform

- decentralized - user is center vs idp . decentralized party will make a claim and issues a digital id and give it to the user who stores it in their digital vault and then a trust system verifies the digital ids for all parties

Authentication - Proving who you are 
Authorization (AuthZ) - What I can access 


## AD and Azure AD

### Entra/Azure AD
Entra: IDP for MSFT clouds such as azure, o365 and dynamics 365. Also it is not just AD in the cloud. supports oauth, saml, https 

- identity - object that can be authentified 
- users 
- groups
- apps will have their own object as well
- Devices can live inside of AzureAD. 
    - registered can be used for stuff like byob or their personally. Can be used for mac os, ubuntu 20.XX+ , android and more
    - joined is for corporate owned devices. Only works with Windows 10+ and Server 19+ in Azure
- Password Hash sync: The ability to sync between Azure/EntraAD and an on Prem ad to grant acess by checking the hash of the user's password hash.
- Passthrough authentication :AzureAD/Entra sends request to a service bus , which is then sent down to an on prem AD for authentication and the results are sent back through to let Azure send the results to the user
- Cloud and federated authentication : Goes through a federation servie which is then checked by AD. Benefits related to locked accounts. Not recommended because after initial auth it isn't used because just the token is used which can be hijacked , etc 
- Azure has the ability to check darkweb passwords against hash of the hash. 

### For Hybrid enviornments
- AD is always the source of truth. Sync is one way except for some limited services like password write back
- An Azure AD instance can only sync from on AzureAD connect
- One AD can sync to multiple Azure tenants/instances 

## Roles and Administrative Units
- Roles: A set of permissions that can be applied to users. The only groups that can recieve roles are security groups 
- Administrative Units - Don't inherit memembers of the groups in these units. Users must be explicilty added to the administrative units. Can use dynamic membership or static to add users or groups to a admin unit. Need a P1 license to manage an AU. 
Always use least privilege

## Privileged Identity Management (PIM)
- Enables elevation of EntraAD roles when needed
- Can also be used to eleavte to a priviledge group for limited time
- Roles must be pre-assigned to available users
- Just in time solution
- Can be permanent or also temporarily 

Access Reviews - review group memeberships and permission to ensure the user has just the access they need

Mfa - stops alot of lazy attacks 
MFA fatigue - users will eventually click to grant access if prompted to much. a P1 license is needed to implement mfa or use Security Defaults (or be GLobal Admin)

Typically access tokens have a TTL and must be refreshed

Context matching - can pass on relevant information such as application name, location, and more



Federate - allows you to trust tokens from other services 

## Differences between AD & AzureAD
AD introduced in 2000

Federation glues an on prem to Azure AD to allow for seamless management. Uses SAML tokens . Allows you to use a single identity for both on prem and azure access provisioning

Pain Points
- Rotate tokens
- Must maintain federation infrastructure which is publically facing. 

AzureAD - Cloud based identity provided. There is no "Domain Controllers" for an Azure AD domain
- SCIM: provides it for cross domain authentication
- SAML
- NO KEREBEROS
- NO NTLM
- NO LDAP
-


## Conditional Access and MFA

## Just-in-time Permissions

### Resources
- [Module 2 - Identity](https://youtu.be/6Vm-h_3nKjc?si=rqULd2r7ZJyPLKz7)
- [The Line Between AD and Azure AD](https://youtu.be/uts0oy8NlUs?si=l0R4lmFeCTrtDXe5&t=1087)