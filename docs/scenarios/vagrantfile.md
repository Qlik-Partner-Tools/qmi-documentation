## Vagrantfile
This file is a simple set of instructions built in Ruby that tells QMI how and what to build. This file is used to create the scenario and configure the virtual machine.

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.6.2"

# Relative path where 'shared-content' can be found
sharedContentRelativePath = '../shared-content'

require 'json'
# Module dependency for custom VM values setup
require File.dirname(__FILE__) + '/' + sharedContentRelativePath + '/scripts/custom-setup.rb'

# Load scenario data configuration file
scenario = JSON.parse(File.read(File.join(File.dirname(__FILE__), 'scenario.json')))
# Overwrite of VM values (cpus, memory) from custom values setup in QMI client
vals = CustomSetup.getValues( scenario )["servers"][0]


# Vagrant intialization
Vagrant.configure("2") do |config|

    config.vm.define vals["name"]
    config.vm.box = vals["box"]
    config.vm.network "private_network", ip: vals["ip"]
    config.vm.hostname = vals["name"]

    config.vm.provider :virtualbox do |v, override|
        v.name = vals["name"]
        v.linked_clone = true
        # v.customize ['setextradata', :id, 'GUI/ScaleFactor', '1.25']
        v.customize ["modifyvm", :id, "--memory", vals["memory"]]
        v.customize ["modifyvm", :id, "--cpus", vals["cpus"]]
        v.customize ["modifyvm", :id, "--vram", 64]
        v.customize ["modifyvm", :id, "--clipboard", "bidirectional"]

    end

    # Shared synced folders setup (Host <-> Guest)
    config.vm.synced_folder "./files", "c:/installation/"
    config.vm.synced_folder sharedContentRelativePath, "c:/shared-content/"

    # Provision scripts execution
    config.vm.provision :shell, path: sharedContentRelativePath + "/scripts/modules/q-bootstrap.ps1"
    config.vm.provision :shell, path: "./scripts/provisioner.ps1"

end
```