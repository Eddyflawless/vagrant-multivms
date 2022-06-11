# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"

  servers = [
    {
      :hostname => "Server1",
      :box => "hashicorp/bionic64",
      :ip => "192.168.56.24",
      :ssh_port => "220"
    },
    {
      :hostname => "Server2",
      :box => "hashicorp/bionic64",
      :ip => "192.168.56.26",
      :ssh_port => "221"
    }
  ]

  servers.each do |server|

    config.vm.define server[:hostname] do |node|
        node.vm.box = server[:box]
        node.vm.hostname = server[:hostname]
        node.vm.network :private_network, ip: server[:ip]
        node.vm.network "forwarded_port", guest: 22, host: server[:ssh_port], id: "ssh"
        node.vm.provision "file", source: "./index.html", destination: "/home/vagrant/index.html"

        node.vm.synced_folder "./data", "/vagrant_data"

        # config.vm.provision "shell", inline: <<-SHELL
        #   apt-get update
        #   apt-get install -y apache2
        # SHELL

        config.vm.provider "virtualbox" do |vb|
        
          # Customize the amount of memory on the VM:
          vb.memory = "256"
          
        end

    end

  end
  

end
