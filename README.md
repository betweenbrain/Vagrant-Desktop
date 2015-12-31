Use by:

````
$ vagrant box add [boxname] [url]    
$ vagrant init [boxname]    
$ vagrant up    
````

Abbreviated `Vagrantfile` to use:

````
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # Every Vagrant development environment requires a box.
  config.vm.box = "lubuntu-desktop"

  # Share an additional folder to the guest VM.
  config.vm.synced_folder ".", "/home/vagrant",
    owner: "vagrant",
    group: "vagrant",
    mount_options: ["dmode=775,fmode=664"]

  # Display the VirtualBox GUI when booting the machine
  config.vm.provider "virtualbox" do |vb|
     vb.gui = true
   end
end
````
