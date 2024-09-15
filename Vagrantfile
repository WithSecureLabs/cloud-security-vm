# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-24.04"
  config.vm.synced_folder "./data", "/hostdata"

  config.vm.provider "virtualbox" do |vb|
    # Don't display the VirtualBox GUI when booting the machine - change to true if you want the GUI
    vb.gui = false
    # Customize the amount of memory on the VM:
    vb.memory = "4096"
  end

  # Provision cloud tools into VM
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
