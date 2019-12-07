# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-18.04"
  config.vm.network "private_network", ip: "192.168.33.10"

  case RUBY_PLATFORM
    when /mswin|msys|mingw|cygwin|bccwin|wince|emc/
        # Fix Windows file rights, otherwise Ansible tries to execute files
        config.vm.synced_folder "../", "/vagrant", type:"virtualbox", :mount_options => ["dmode=755","fmode=644"]
    end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "/vagrant/CKAN-in-Vagrant/playbook.yml"
    ansible.inventory_path = "/vagrant/CKAN-in-Vagrant/inventories/vagrant"
    ansible.limit = "all"
  end
end
