# -*- mode: ruby -*-
# vi: set ft=ruby :

hostname = 'win10ws1'

Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox"

  # Development Workstation -----------------------------------------
  config.vm.define "workstation", primary: true do |workstation|
    # Windows 10
    # https://app.vagrantup.com/jacqinthebox/boxes/windows10
    # https://github.com/jacqinthebox/packer-templates
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
