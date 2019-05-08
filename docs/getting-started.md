# Getting Started
The QMI getting started guide will walk you through the installation and configuration of the components that QMI utilises.

QMI is built on the shoulders of industry leading and industry standard technologies and has been tested with Microsoft Windows, Apple OSX and various flavours of Linux (Ubuntu, CentOS).

## Getting the pre-requisites
### Downloads
1. <a href="https://www.packer.io/downloads.html" target="_blank">Hashicorp Packer</a>
2. <a href="https://www.vagrantup.com/downloads.html" target="_blank">Hashicorp Vagrant</a>
3. <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">Oracle VirtualBox</a>

Note: As these technologies are Open Source there can at times be incompatibilities between versions.  Be sure to review the documentation on these applications before upgrading.

### Installation
Install the applications as per the documentation for each application.

#### Clone or download the Git repositories
1. <a href="https://github.com/Qlik-Partner-Tools/qlik-base-os" target="_blank">Base Operating System</a>
2. <a href="https://github.com/Qlik-Partner-Tools/qmi-scenarios" target="_blank">Vagrant QMI scenarios</a>

#### Initialise the Shared-Content folder for QMI scenarios
The shared-content folder contains all script modules that are used in the base QMI provided scenarios.

Launch your favourite terminal or PowerShell and enter 

```
cd /qmi-scenarios
./init-shared-content.sh
```