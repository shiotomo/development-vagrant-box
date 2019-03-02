# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # config.vm.box = "bento/ubuntu-18.04"
  # config.vm.hostname = 'rx7'
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 3000, host: 3000
  # config.vm.network "forwarded_port", guest: 4567, host: 4567
  # config.vm.network "private_network", ip: "192.168.33.11"

  config.vm.define :master do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'master'
    server.vm.network "private_network", ip: "192.168.33.11"
    server.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y python-minimal
    SHELL
    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook/master_installer.yml"
      ansible.inventory_path = "settings/master/hosts"
      ansible.limit = "all"
    end
  end

  config.vm.define :develop do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'develop'
    server.vm.network "private_network", ip: "192.168.33.12"
    server.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y python-minimal
    SHELL
    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook/develop_installer.yml"
      ansible.inventory_path = "settings/develop/hosts"
      ansible.limit = "all"
    end
  end

  config.vm.define :monitor do |server|
    server.vm.box = "bento/ubuntu-18.04"
    server.vm.hostname = 'monitor'
    server.vm.network "private_network", ip: "192.168.33.13"
    server.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y python-minimal
    SHELL
    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook/monitor_installer.yml"
      ansible.inventory_path = "settings/monitor/hosts"
      ansible.limit = "all"
    end
  end

  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get update
  #   sudo apt-get -y upgrade
  #   sudo apt-get install -y python-minimal
  # SHELL

  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook/all.yml"
  #   ansible.inventory_path = "settings/hosts"
  #   ansible.limit = "all"
  # end
end
