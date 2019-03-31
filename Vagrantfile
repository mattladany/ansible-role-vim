# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Ubuntu 16.04
  config.vm.define "trusty" do | trusty |
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.network "public_network", ip: "192.168.1.22"
  end

  # Centos 7
  config.vm.define "centos" do | centos|
    centos.vm.box = "centos/7"
    centos.vm.network "public_network", ip: "192.168.1.23"
  end

  config.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "1024"
   end

end
