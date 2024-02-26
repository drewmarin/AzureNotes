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
- Cloud and federated authentication 


### For Hybrid enviornments
- AD is always the source of truth. Sync is one way except for some limited services like password write back
- An Azure AD instance can only sync from on AzureAD connect
- One AD can sync to multiple Azure tenants/instances 



Federate - allows you to trust tokens from other services 

## Conditional Access and MFA

## Just-in-time Permissions

### Resources
[Module 2 - Identity](https://youtu.be/6Vm-h_3nKjc?si=0JNBGnE1cxoYmtlZ&t=3028)