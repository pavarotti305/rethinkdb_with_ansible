# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config| 

  # General Vagrant VM configuration.
    config.vm.box = "ubuntu/trusty64"
    config.ssh.insert_key = false
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "forwarded_port", guest: 443, host: 8443
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.linked_clone = true
  end
  # Rethink db server 1.
  config.vm.define "rethinkdb1" do |dbservers|
    dbservers.vm.hostname = "orc-rethinkdb1.dev"
    dbservers.vm.network "private_network", ip: "172.16.25.10"
  end
  # Rethink db  server 2.
  config.vm.define "rethinkdb2" do |dbservers|
    dbservers.vm.hostname = "orc-rethinkdb2.dev"
    dbservers.vm.network "private_network", ip: "172.16.25.20"
  end

  # Rethink db server 3.
  config.vm.define "rethinkdb3" do |dbservers|
    dbservers.vm.hostname = "orc-rethinkdb3.dev"
    dbservers.vm.network "private_network", ip: "172.16.25.30"
    end
end