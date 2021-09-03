# Authentication

Type of challenge : **Learning/Practice**

Duration : **8 hours**

Team Challenge : **solo**

## Learning objectives

At the end of this challenge you should be able to :
- Enable MFA
- Enable passwordless authentication
- Setup and report password policies
- Setup password reset self-service
- Setup conditional access

## Your mission

Most employees at Becloud are happily working in remote but some of them still complains about the fact that they have to remember too much passwords to access each company's resource. We will try to unify the authentication across all resources.

Since all resources don't have the same business criticality, it seems normal that the authentication type will depend on the type of resource accessed.

We will ask you to create a group for each authentication type and setup the conditional access rules to enforce the authentication type.

Since we still don't have resources configured in our Azure tenant, we will test it by trying to login with a non admin user account to the azure portal.

To summarize, your mission will be to setup these different authentication methods to login to the azure portal :

- Strong password enforced
- MFA enabled
- Passwordless (Authenticator, SMS)

Since you will not be alone to maintain this infrastructure, we will ask you to report every setting that you changed for each configuration into a documentation file.

Following you, which authentication method is the more vulnerable? Could you sort the authentication method by security? What are the risks with each authentication method?
### Instructions

* Create groups corresponding to the different auth methods
* Create the conditional access policies that will enforce secure login into azure apps
* Enable password reset self-service
* Report each settings into a documentation file
* Try each authentication method with your user

## Trusty Resources

- ["Azure Active Directory Authentication" - Microsoft](https://docs.microsoft.com/en-us/azure/active-directory/authentication/)
- ["Azure AD device identity" - Microsoft](https://docs.microsoft.com/en-us/azure/active-directory/devices/)
