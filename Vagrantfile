# -*- mode: ruby -*-
# vi: set ft=ruby :

hostname = 'win10ws1'

Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox"

  # Development Workstation -----------------------------------------
  config.vm.define "workstation", primary: true do |workstation|
    # Ubuntu 18.04.2 LTS (Bionic Beaver)
    # https://app.vagrantup.com/ubuntu/boxes/bionic64
    # http://cloud-images.ubuntu.com/bionic/
    workstation.vm.box = "jacqinthebox/windows10"
    workstation.vm.hostname = hostname
    workstation.vm.network :private_network, ip: "192.168.56.51"
    workstation.vm.provider "virtualbox" do |vb|
      vb.linked_clone = true
      vb.customize ["modifyvm", :id, "--memory", 2048]
      vb.customize ["modifyvm", :id, "--name", hostname]
      vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    end
  end
end
