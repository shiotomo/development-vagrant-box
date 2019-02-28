# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # config.vm.box = "bento/ubuntu-18.04"
  # config.vm.hostname = 'rx7'
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 3000, host: 3000
  # config.vm.network "forwarded_port", guest: 4567, host: 4567
  # config.vm.network "private_network", ip: "192.168.33.11"
  #
  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook/install.yml"
  #   ansible.inventory_path = "settings/hosts"
  #   ansible.limit = "all"
  # end


  config.vm.define :master do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'master'
    config.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.define :develop do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'develop'
    config.vm.network "private_network", ip: "192.168.33.12"
  end

  config.vm.define :monitor do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'monitor'
    config.vm.network "private_network", ip: "192.168.33.13"
  end

end
