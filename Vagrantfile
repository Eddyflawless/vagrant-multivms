# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "MyAnsibleServer1", primary: true do |node|
    
      node.vm.box = "hashicorp/bionic64"
      node.vm.hostname = "MyAnsibleServer1"
      node.vm.network "private_network" , ip: "192.168.56.25"
      node.vm.network "forwarded_port", guest: 80, host: 7070 

  end

  config.vm.define "MyAnsibleServer2" do |node|
    
      node.vm.box = "hashicorp/bionic64"
      node.vm.hostname = "MyAnsibleServer2"
      node.vm.network "private_network" , ip: "192.168.56.27"

  end

  config.vm.synced_folder "./data-share", "/vagrant_data"

  config.vm.provision "ansible_local" do |a|
    a.playbook = "./ansible/playbook.yaml"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end
 

end
