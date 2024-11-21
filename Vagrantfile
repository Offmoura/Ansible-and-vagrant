# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_check_update = false

  #Ansible master
  config.vm.define "master" do |master|
  config.ssh.insert_key = false
    master.vm.hostname = "ansible-master"
    master.vm.box = "centos/8"
    master.vm.network :private_network, ip: "10.0.0.101"
  end

  #node 1
  config.vm.define "node1" do |node1|
    node1.vm.hostname = "node-1"
    node1.vm.box = "ubuntu/trusty64"
    node1.vm.network :private_network, ip: "10.0.0.102"
  end

  #node 2
  config.vm.define "node2" do |node2|
    node2.vm.hostname = "node-2"
    node2.vm.box = "generic/rhel8"
    node2.vm.network :private_network, ip: "10.0.0.103"
  end

  config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.memory = "2048"
     vb.cpus = 2
  end
end