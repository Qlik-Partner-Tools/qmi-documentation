## Files Folder

The files folder should contain any files that you want to provision with the scenario.
For example the qmi-qs-sn (Qlik Machine Image – Qlik Sense – Single Node) scenario contains the following.

This folder will be shared with the guest virtual machine and can provide the provisioning scripts with content.

| Name | Description |
| ------------| ------------|
| apps | Any applications stored in this folder, or folders within this folder will be imported into Qlik Sense and published to the folder name. |
| extensions | Any extensions stored in this folder will be imported into Qlik Sense. |
| qs-cfg.json | This file contains configuration information used in the provisioning of Qlik Sense.|
| sp_config.xml | This XML file is used by the Qlik Sense installer to configure Shared Persistence. |