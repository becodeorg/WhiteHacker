# 1. RBAC Introduction
## Role Assignment Concepts
- Securtiy principal
- Role Definition
- Scope

### **Security Principals**
A Security Principal is a collection of individuals, we might call that a group, an application or a service that requires access to an Azure resource, and that can be any Azure resource.

 - **Individuals** : Individuals are represented as Azure Active Directory users, and maybe a user in another tenancy depending on how you've configured Azure Active Directory
 
 - **AD GROUP** : A collection of individuals is represented as an Azure Active Directory group
  
 - **Service Principal** : Now interestingly, applications and services can be represented as a thing called a service principal

### **Role Definitions**
#### What's a Role Definiton ?
- It's a collection of permissions
- A role definiton is expressed as a set of operations that can be performed (Ex: Read, Write, Delete)

### **Scope**
#### What's a Scope ?
- It's the boundary that a Role Definition applies to
- Can be assigned at four level (Management group, Subscription, Resource group, Resource)
>Access at parent scope is inherited at child scope.

## Why RBAC ?
1. Ensure that the principle of least privilege is used
   - Only required access is granted
   - Minimize damage during account compromise
2. Reduce chance of unauthorized actions being performed
3. Reduce chance of accidental actions being performed

### How RBAC Determines Access
1. Security principal acquires token for ARM (Azure resource manager)
2. REST API call made to ARM with token attached
3. ARM retrieves all role assignments and deny assignments that apply to resource
against which action is occurring
4. ARM determines role assignments that apply to security principal for this
resource
5. ARM determines if the action in the API call is included in the roles the security principal has for resource
6. If the security principal doesn’t have a role with that action in the requested
scope, access not granted
7. If deny assignment applies, access is blocked

### RBAC Drawbacks
1. Increases in security impose necessary limitations
2. Selecting roles for users requires a good understanding of the specific tasks that
individuals need to be able to perform
   - Only provision privileged users with specific tools rather than entire toolbox
   - May mean that extra time is required when nature and scope of the task to be
carried out is misjudged

### Is RBAC Appropriate?
Here are some question you should ask yourself before using RBAC:
1. How many individuals at the organization interact with the subscription?
2. Would the organization be better off if the individuals that interacted with the subscription had restricted permissions?
3. Are other security measures, such as privileged identity management, in place to protect privileged accounts?

### RBAC vs AD ROLES
Azure AD Admin Roles are different from Azure RBAC Roles
- Use Azure RBAC roles to manage permissions to Azure resources
- Use Azure AD administrator roles to manage permissions to Azure AD resources

Differentiating Azure RBAC and Azure AD Administrator Roles :
|Azure RBAC Roles|Azure AD Administrator Roles|
|-|-|
|Used to manage access to Azureresources|Used to manage access to Azure Active Directory resources|Can create custom roles Can only use built-in roles|
|Scope can be configured at the following levels: Management group, Subscription, Resource group, Resource| Only scoped at the tenant level|
|Access role information using Azure portal, Azure CLI, Azure PowerShell, Azure ARM templates, REST API|Access role information through Azure portal, Office 365 admin portal, Microsoft Graph, Azure AD PowerShell|

### Overlap
- Azure RBAC and Azure AD admin roles don’t overlap by default
- Global admin can manage Azure Subscriptions and Management Groups
- This option gives Global Administrator the User Access Administrator RBAC role for all
subscriptions associated with a tenant

# 2. Azure RBAC Roles
- Roles Definition
- Deny assignments
- Azure RBAC built-in Roles
- RBAC Limits
- Assigning RBAC Roles
- Custom Role definition

# Roles Definition
Okay, so a role definition, generally termed a role, is a collection of permissions and it lists the operations that can be performed. We talked about this in the introductory module. The next thing I want to talk about is a deny assignment. Now, the initial version of Azure role-based access control was allow only and there was no explicit deny assignment.

## Deny assignements
 - Initial version od RBAC was allow-only with no Deny
 - Deny assignement binds a set of deny actions to user/group/servie principal at a particular scope for the purpose of denying access.
 - Can also exclude principals and prevent inheritance to child scopes
 - Deny assignments are read-only
 - Can apply to the Everyone principal

## Azure RBAC built-in Roles
Azure RBAC has over 70 buit-in roles
  - New roles appear regularly
There are four fundamental RBAC roles
  - Owner : Manage everything including access to resources
  - Contributor : Manage everything except resources
  - Reader : Read only access to everything
  - User Access Administrator : Manage user access to Azure resources

Here is the [list](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles) of the built-in roles that belongs to Azure resources

## RBAC Limits
- 5000 Max role assignmnets per subscription
- 5000 Max customs roles per tenant

## Assigning RBAC Roles
RBAC can be assigned in many different ways, which are :
- Azure Portal
- Powershell (New-AzureRmRoleAssignment)
- Azure CLI
- REST API
- ARM Template

## Custom roles definitions
If the Azure built-in roles don't meet the specific needs of your organization, you can create your own custom roles. Just like built-in roles, you can assign custom roles to users, groups, and service principals at management group, subscription, and resource group scopes.

Custom roles can be shared between subscriptions that trust the same Azure AD directory. There is a limit of 5,000 custom roles per directory. (For Azure Germany and Azure China 21Vianet, the limit is 2,000 custom roles.) Custom roles can be created using the Azure portal, Azure PowerShell, Azure CLI, or the REST API.

More about Custom roles definition :
- [Azure custom roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/custom-roles)
- [Understand Azure role definitions structure](https://docs.microsoft.com/en-us/azure/role-based-access-control/role-definitions)

# 3. Auditing RBAC Activity and Configuring Management Access
- Azure Activity Log
- Activity Log vs. Diagnostic Log
- Activity Log Filters
- Management and Conditional Access
  
## Azure Activity Log
RBAC Auditing in a Nutshell is a way to changes are made to role assgnments and definitions

Whenever a change is made to role assignments or role definitions within a subscription, details of those changes are written to the Azure Activity Log (previously Audit Log or Operational Logs).

Azure Activity Log can be directly queried for 90 days

Activity Log data can be stored longer

The following RBAC operations are written to the Azure Activity Log:
- Create role assignment
- Delete role assignment
- Create or update custom role definition
- Delete custom role definiton
  
Azure Activity Log Allows you to determine "who, what & when" for write (PUT, POST, DELETE) operations performed on a subscription, It can retrieve events from Portal, CLI, Powershell & Azure Monitor REST API

Azure Activity Log can :
- Export data to csv
- Analyze log data using Azure Log Analytics
- Store data up to 2147483647 days by configuring a log profile

Log profiles allow Activity Log telemetry to be stored in a storage account

## Activity Log vs. Diagnostic Log
|Activity Log|Diagnostic Log|
|-|-|
|Activity Log provide data about external operations that are performed on a resource by management activity|Diagnostic Logs provide data about the operation of Azure resources|
|Provides visibility on the Control Plane|Provide visibility on the Data Plane|

## Activity Log Filters
Event category :
- Administrative
  
Operation :
- Create role assignment
- Delete role assignment
- Create or update role assignment definition
- Delete custom role definition

## Management and Conditional Access (Risky Sign-in)
In Azure you have the ability to restrict management of Azure using what's called a conditional access policy. Now to do this requires that you have Azure Active Directory P2 and that, when you implement this, it applies to all management endpoints including the portal, the ARM provider, PowerShell, and the CLI. So, what's conditional access do? Well basically it allows access to particular resources once certain conditions have been met, and conditions can include sign-in risk, which is where a calculation is performed to determine whether or not a sign-in attempt wasn't made by the owner of an Azure account. For example, let's say you sign in from Sydney and then half an hour later there is a sign in from Mozambique. That would be an elevated sign-in risk simply because it's pretty difficult to get from Sydney to Mozambique in half an hour unless you have a Star Trek transporter. Another conditional access condition you can configure is your device platform. You can come back and say I'm only going to allow people to access Azure management functionality if they're on Windows or macOS. If they're using Android or iOS, bad luck, you can't do it. Specify your device state. If the device is Azure AD joined or is listed as compliant, depending on how you're managing it, and whether or not you want to specify that management can only be performed from a specific location. You might say, right, we're only going to allow someone to perform Azure management functions if they're coming from a very specific range of IP addresses.

This feature requires Azure AD P2, and applies to all Azure Management Endpoints including Azure Portal, ARM provider, Azure Powershell, Azure CLI

Check the documentation for more about that feature: <br />
[Conditional Access: Sign-in risk-based Conditional Access](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)

