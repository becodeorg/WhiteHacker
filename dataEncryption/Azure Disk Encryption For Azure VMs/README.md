# Azure Disk Encryption For Azure VMs
Type of challenge : **Learning/Practice** <br />
Duration : **1 day** <br />
Team Challenge : **solo** <br />

## Preamble
If you're using IaaS in Azure and deploying virtual machines, you might be curious about how encryption works with those virtual machines, where is encryption for data at rest applied, and what are the ways to add additional encryption to those virtual machines for your very sensitive workloads. That's what we're going to be covering in this briefing. The first thing we're going to learn about is what are the supported encryption options when it comes to virtual machines. There's a few different options, and it's important to understand when you would apply encryption, and what encryption exists already. In order to use Azure Disk Encryption on Azure VMs, there are some prerequisites that have to be in place, and there's some general requirements in order for encryption to be supported.

## Learning objectives
- How to implement Azure Disk Encryption on both Existing and New Virtual Machine (BitLocker)
- How to implement Azure Disk Encryption on both Existing and New Virtual Machine (DM-Crypt)

## Your mission
As an administrator at Privacy Corp, a super company that is specialized in data privacy, you have been asked to make sure that every single virtual machine deployed in the cloud has Data Encryption enabled for the OS disk and the Data disk(s) using BEK (BitLocker encryption Key). So you will first start to implement that manualy using the Azure Portal, then for you to make this process conscitent over time, you have been asked to write a Powershell script that deploys all need ressources to be able to deploy a virtual machine with Azure Disk Encryption enabled (BitLocker).


## Nice to have
A Powershell script that deploys all need ressources to be able to deploy a linux virtual machine with Azure Disk Encryption enabled (DM-Crypt) with Key Vault encryption Key for additional security level).

## Trusty Resources
- [Azure Disk Encryption for Windows](https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/azure-disk-enc-windows)
- [Create and configure a key vault for Azure Disk Encryption on a Windows VM](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/disk-encryption-key-vault)
- [Azure Disk Encryption sample scripts](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/disk-encryption-sample-scripts)
- [Azure Disk Encryption for Linux VMs](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/disk-encryption-overview)
- [Azure Disk Encryption scenarios on Linux VMs](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/disk-encryption-linux)
<br />
<br />

[< Back](../README.md)
