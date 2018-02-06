1. Can I change the location virtual machines are stored?
    Yes, this is set within virtualbox preferences. The default location is:
       * Windows: C:\Users\USERNAME\VirtualBox VMs
       * Mac OS X and Linux: ~/VirtualBox VMs
* Can I change the location where box files are located?
    The environment variable VAGRANT_HOME can be set to change the directory where Vagrant stores global state. By default, this is set to ~/.vagrant.d. The Vagrant home directory is where things such as boxes are stored, so it can actually become quite large on disk.

    Usually this location is by default set to:
    * Windows: C:/Users/USERNAME/.vagrant.d/boxes
    * Mac OS X and Linux: ~/.vagrant.d/boxes
* How many machines I can have 'RUNNING' at the same time?
    It really depends on the size of your local machine. The more RAM you've got the bigger the number of Qlik Machines you can run at the same time (in RUNNING state). It's recommended not have more than 3/4 as an average. However, you can have as many as you like if they are SUSPENDED or POWEROFF.

* I want to access Windows of a specific scenario, how do I do it?
    You can only access Windows for already provisioned scenarios.
    Open VirtualBox application and double click on the virtual machine you like to access. You'll access Windows logged-in as 'vagrant' user.

* QMI seems to take quite a lot of disk space!, what should I do?
    FAQ 1 an 2 help you change location where Qlik Machines and boxes are stored.

* VT-x is disabled in BIOS.
    If you get an error saying "VT-x is disabled in BIOS" (or similar) that means Virtualization Technologies are disabled in your machine and you won't be able to run virtual machines in it.

    You can change this setting by entering BIOS at reboot. If you don't feel confident enough to change this setting yourself, please contact IT.

* Should I let Virtualbox or Vagrant updates?
    The important thing to check is compatibility between VirtualBox and Vagrant.
    * Vagrant 2.0.2
    * VirtualBox 5.1.26
    Updating or using newer versions shouldn't break QMI but do so at your risk, :-)

* Error while provision: The ‘reload’ provisioner could not be found
    Some scenarios need specific plugins to be installed prior provision. To list current installed plugins, type the following on a terminal window.

    vagrant plugin list
    Make sure vagrant-reload, reload, vagrant-windows-sysprep and vagrant-disksize are on the list. If any of them doesn't show up type the following to install:

    vagrant plugin install vagrant-reload reload vagrant-windows-sysprep vagrant-disksize
    It may also rarely happen while installation of plugins you end up getting errors resolving dependencies. This command re-installs all current installed plugins resolving those dependencies:

    vagrant plugin expunge --reinstall