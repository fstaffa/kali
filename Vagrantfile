# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # The name of the box to use. For our use case, this is the name specified as part
  # of the `vagrant box add` command.
  config.vm.box = "kalirolling-2019-2"

  config.ssh.username = 'root'
  config.ssh.password = 'toor'
  config.ssh.insert_key = 'true'

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--vram", "16"]
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ["modifyvm", :id, "--usbehci", "on"]
    vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'Atheros', '--vendorid', '0x0cf3', '--productid', '0x9271']
  end

  # Run an ansible playbook within the Vagrant VM. For examples of other provisioners
  # and their usage, please see the Vagrant website
  #
  #config.vm.provision "ansible_local" do |ansible|
  #  ansible.playbook = "scripts/common-cli.yml"
  #  ansible.install_mode = "pip"
  #end
  
  config.vbguest.auto_update = false
end
