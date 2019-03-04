---
layout: post
title: Storage Account Encryption
---

By default storage accounts are encrypted, and microsoft holds the keys.
The encryption that is used is AES 256 bit, as it is one of the strongest cipers currently available.

* Azure storage services:
  * Azure Managed Disks
  * Azure Blob storage
  * Azure Files
  * Azure Queue storage
  * Azure Table storage. 
  * Both performance tiers (Standard and Premium). 
  * Both deployment models (Azure Resource Manager and classic).

The one big issue with this is that Microsoft owns the encryption key and potentially has unrestricted access to the users data.
They have included the facility for the user to specify a encryption key, so you can meet your individul security company or reglatory compliance needs.
To use your own key, you will need.
* A Key Vault 
  * Needs to be in th same region as the storage
  * Does not need to be in the same subscription
* Storage needs permissons to access your Key Vault.
    * Need to grant wrapKey, unwrapKey privileges


## References
* https://docs.microsoft.com/en-us/azure/storage/common/storage-service-encryption
