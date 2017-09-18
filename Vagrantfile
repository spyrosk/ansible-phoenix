# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/trusty64"

    config.vm.provider "virtualbox" do |vm|
      vm.memory = 2048
      vm.cpus = 2
    end

    config.vm.synced_folder "project", "/home/vagrant/project", type: "nfs", create: true

    config.vm.network "private_network", ip: "10.10.10.10"

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.verbose = "vvv"
    end
end