# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos6"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

  config.vm.network "private_network", ip: "192.168.33.10", error_check: false
  config.vm.network "forwarded_port", guest: 80, host: 8000

  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./provision.yml"
    ansible.inventory_path = "./ansible_hosts"
    ansible.limit = "all"
  end


end
