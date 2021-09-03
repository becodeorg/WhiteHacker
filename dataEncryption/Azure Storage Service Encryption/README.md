
# Azure Storage Service Encryption
Type of challenge : **Learning/Practice** <br />
Duration : **1 day** <br />
Team Challenge : **solo/group** <br />


## Preamble
Azure Storage forms the basis for so many things when it comes to encryption for data at rest within Azure. Microsoft makes use of Azure Storage for things like Azure SQL, the Recovery Vault, and Azure VMs. So before we jump into any of those other topics, it makes sense to learn about encryption for Azure Storage. That's what we're going to be covering in this briefing. We're going to be learn about what are the supported encryption options when it comes to Azure Storage. Then we'll learn more specifically about the prerequisites if you want to implement customer-managed keys for a storage account. And then we'll actually go through the process of implementing customer-managed keys for an Azure Storage account.

## Learning objectives
- Learn about data regulation and compliance.
- Learn about encryption for Azure Storage
- Learn to create a Key Vault in Azure
- Learn to configure storage account to use Azure key Vault
- Implementing Custom Managed Keys for Azure Storage

## Your mission
As an administrator at Privacy Corp, a super company that is specialized in data privacy, your security and compliance team has determined that they need to implement customer-managed keys, so you're going to help out with that. You will have to deal with three different things here. First is the storage account itself. And then there is Azure Active Directory, which is what the storage account will use to access Key Vault. So we've got our storage account, and we also have an Azure Active Directory tenant. And then we're also going to create a Key Vault, and that Key Vault is going to store the customer-managed key, the key that we're providing. That key could be generated on-premises in on HSM and then exported through a specialized transfer process. In order for the storage account to be able to talk to Key Vault and access that key for encryption and decryption operations, it's going to need an identity within Azure AD, and then that identity is granted access through an access policy to Key Vault. In that way, the storage account can now retrieve that key to perform the encryption and decryption operations for data that's stored in the storage account.

## Nice to have

A Powershell script that implements the principle of Implementing Custom Managed Keys for Azure Storage.


## Trusty Resources
- [Microsoft compliance offerings](https://docs.microsoft.com/en-us/compliance/regulatory/offering-home)
- [Shared responsibility in the cloud](https://docs.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)
- [Data encryption in Azure](https://docs.microsoft.com/en-us/azure/architecture/framework/security/design-storage-encryption)
- [Azure Data Encryption at rest](https://docs.microsoft.com/en-us/azure/security/fundamentals/encryption-atrest)
- [Azure Storage encryption for data at rest](https://docs.microsoft.com/en-us/azure/storage/common/storage-service-encryption)
- [Azure data security and encryption best practices](https://docs.microsoft.com/en-us/azure/security/fundamentals/data-encryption-best-practices)
- [Customer-managed keys for Azure Storage encryption](https://docs.microsoft.com/en-us/azure/storage/common/customer-managed-keys-overview)
<br />
<br />

[< Back](../README.md)