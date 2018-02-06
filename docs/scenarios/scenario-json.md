## scenario.json file
This file contains information on the scenario. And is used during the creation of the virtual machine.

![scenario-json](../img/scenarios-json.png)

#### Description of scenario.json fields

1. name: The name of the scenario
* description: Text to describe what the scenario contains
* category: Category of scenario
* plugin-dependencies: Description of the Vagrant plug-ins that are required to run the scenario
* notes: Any information you wish to advise the user on
* version: Version of the scenario
* author: Name of the Author
* email: Email address
* disabled: Currently not used
* qlik-default-binary: The Qlik software to use by default
* resoures: URLS to present at the end of provisioning to enable users to connect
* config
    1. allowUpdates: Currently not used
    * Servers
        1. name: The name that will be the hostname of the server
        * ip: the IP address to assign the server
        * box: the name of the Vagrant box to use
        * memory: Amount of RAM to allocate
        * cpus: The number of cores to allocate
        * sense
            1. central: if the server is a central node
            * proxy: Currently not used
            * persistence: Shared or Sync