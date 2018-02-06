# Getting Started
The QMI getting started guide will walk you through the installation and configuration of the components that QMI utilises.

QMI is built on the shoulders of industry leading and industry standard technologies and has been tested with Microsoft Windows, Apple OSX and various flavours of Linux (Ubuntu, CentOS).

## Getting the pre-requisites
### Downloads
1. [Hashicorp Packer](https://www.packer.io/downloads.html)
2. [Hashicorp Vagrant](https://www.vagrantup.com/downloads.html)
3. [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Note: As these technologies are Open Source there can at times be incompatibilities between versions.  Be sure to review the documentation on these applications before upgrading.

### Installation
Install the applications as per the documentation for each application.

### Clone or download the Git repositories
1. [Base Operating System](https://github.com/Qlik-Partner-Tools/qlik-base-os)
2. [Vagrant Scenarios](https://github.com/Qlik-Partner-Tools/qmi-scenarios)

### Initialise the Shared-Content Folder
The shared-content folder contains all script modules that are used in the base QMI provided scenarios.

Launch your favourite terminal or PowerShell

```
cd /qmi-scenarios
./init-shared-content.sh
```