# Foreman AzureRm Plugin

## Description
```foreman_azure_rm``` adds [Microsoft Azure Resource Manager](http://azure.com/) as a compute resource for The Foreman

* Website: [TheForeman.org](http://theforeman.org)
* Support: [Foreman support](http://theforeman.org/support.html)

## Installation

### Bundle (Gem)

Add the following to bundler.d/Gemfile.local.rb in your Foreman installation directory (/usr/share/foreman by default)

```bash
$ gem 'foreman_azure_rm'
```

Or simply:

```bash
$ echo "gem 'foreman_azure_rm'" > /usr/share/foreman/bundler.d/Gemfile.local.rb
```

Then run `bundle install` from the same directory

### Package
```
# yum install tfm-rubygem-foreman_azure_rm
```

### Foreman Installer
```
# foreman-installer --enable-foreman-plugin-azure
```

### Development Setup

Clone the repo from github:
```bash
git clone https://github.com/theforeman/foreman_azure_rm.git
```

Add the following to bundler.d/Gemfile.local.rb in your Foreman development directory

```ruby
$ gem 'foreman_azure_rm', :path => 'path to foreman_azure_rm directory'
```

Then run `bundle install` from the same directory

## Features
* Support for most typical IaaS operations
    * VM creation
    * Provisions using Finish and User data templates from Foreman
    * Supports cloud-config provisioning
    * Currently supports single NIC
    * Currently supports single default OS Disk
    * Currently supports only provisioning of Linux platforms
    * Provisioning using [Public Images](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/cli-ps-findimage)
    * Static or dynamic addresses on a per NIC basis
* Limited extension support
    * Microsoft's custom script extension
    * Puppet Lab's Puppet agent extension for Windows

## Configuration
Go to **Infrastructure > Compute Resources** and click on "New Compute Resource".

Choose the **Azure Resource Manager provider**, and fill in all the fields. You need a Subscription ID, Tenant ID, Client ID and a Client Secret which you can generate from your [Microsoft Azure subscription](https://docs.bmc.com/docs/cloudlifecyclemanagement/46/setting-up-a-tenant-id-client-id-and-client-secret-for-azure-resource-manager-provisioning-669202145.html#SettingupaTenantID,ClientID,andClientSecretforAzureResourceManagerprovisioning-SetupTenantIDPrereqPrerequisites)

That's it. You're now ready to create and manage Azure resources in your new Azure Resource Manager compute resource. You should see something like this in the Compute Resource page:


![](https://i.imgur.com/4ClZhTP.png)


![](https://i.imgur.com/eFHucdb.png)


![](https://i.imgur.com/YjlRQIE.png)

    
## Planned Features
* Multiple NICs support
* Support to add multiple data disks (standard or premium)
* Provision using custom images
* Provision using shared image galleries
* Improved extension support    
    
## Known Limitations
* Please note that currently username is expected to be the same on both Virtual Machine tab for Host creation and during Image creation for Compute Resource. The password field for Image creation is optional.
* Unable to provision using Windows Images

## Links
* [Issue tracker](https://projects.theforeman.org/projects/azurerm)
