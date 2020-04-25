# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.8.0"

Vagrant.configure(2) do |config|

  config.vm.box = "centos/7"

  config.vm.network "private_network", ip: "192.168.33.15"

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.limit = "all"
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "hosts"
  end
end
