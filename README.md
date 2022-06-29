# Docker swarm mode cluster setup using Vagrant/Virtualbox

## Cluster up
- Install vagrant and virtual box: [link](https://www.vagrantup.com/downloads)
- Close this repo (or just copy the Vagrant file to a directory)
- Bring up 3 nodes: `vagrant up`
- SSH to node-01: `vagrant ssh node-01`
- Check cluster status: `sudo docker node ls`
- Explore service deployment etc: [link](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)

## Stack demo
https://docs.docker.com/engine/swarm/stack-deploy/

## Ansible vault token
```
o8dniqo3z6n6f51tkkda04s6n
```
