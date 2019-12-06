# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-18.04"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.synced_folder "../", "/vagrant"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "/vagrant/CKAN-in-Vagrant/playbook.yml"
    ansible.inventory_path = "/vagrant/CKAN-in-Vagrant/inventories/vagrant"
    ansible.limit = "all"
  end
end
