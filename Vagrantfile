# -*- mode: ruby -*-
# vi: set ft=ruby :

box = "ubuntu/focal64"

Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    sudo apt-get remove docker docker-engine docker.io containerd runc -y
    sudo apt-get install ca-certificates curl gnupg lsb-release -y
    sudo mkdir -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
  SHELL

  config.vm.define 'node-01' do |node|
    node.vm.box = box
    node.vm.network "private_network", ip: "10.10.8.10"
    node.vm.hostname = "node-01"
  end
  config.vm.define 'node-02' do |node|
    node.vm.box = box
    node.vm.network "private_network", ip: "10.10.8.11"
    node.vm.hostname = "node-02"
  end
  config.vm.define 'node-03' do |node|
    node.vm.box = box
    node.vm.network "private_network", ip: "10.10.8.12"
    node.vm.hostname = "node-03"
  end
end
