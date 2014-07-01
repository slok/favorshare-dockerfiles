# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

box = 'ubuntu/trusty64'
hostname = 'dockerfiles.favorshare'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = box
  config.vm.host_name = hostname
  config.vm.network :private_network, ip: "192.168.100.55"

  #config.vm.network :forwarded_port, guest: 80, host: 8080 # Nginx
  #config.vm.network :forwarded_port, guest: 8125, host: 8125, protocol: 'udp' # statsD

  config.vm.synced_folder ".", "/home/vagrant/dockerfiles"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
    ansible.inventory_path = "hosts-dev"
    ansible.verbose = "v"
    ansible.host_key_checking = false
    ansible.limit = 'devserver'
  end
end