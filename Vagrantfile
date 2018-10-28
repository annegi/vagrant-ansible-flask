# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.name = "mydev01"
    v.memory = 1024
    v.cpus = 2
  end

  config.vm.hostname = "mydev01"
  config.vm.network :private_network, ip: "10.10.10.20"

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/inventory"
    ansible.become = true
  end

end
