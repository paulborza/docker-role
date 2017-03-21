# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.define "ubuntu-xenial" do |machine|
    machine.vm.box = "ubuntu/xenial64"
    machine.vm.provision "shell", inline: "apt-get update && apt-get install -y python"
    machine.vm.provision "ansible" do |ansible|
      ansible.playbook = "tests/vagrant.yml"
    end
  end
end
