# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu"
  config.vm.hostname = 'rx7'
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 4567, host: 4567

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook/main.yml"
    ansible.playbook = "playbook/rbenv.yml"
    ansible.inventory_path = "settings/hosts"
    ansible.limit = "all"
  end

  config.vm.network "private_network", ip: "192.168.33.11"
end
