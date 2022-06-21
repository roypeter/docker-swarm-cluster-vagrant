# Docker swarm mode cluster setup using vagrant/virtualbox

## Cluster up
- Install vagrant and virtual box: [link](https://www.vagrantup.com/downloads)
- Close this repo (or just copy the Vagrant file to a directory)
- Bring up 3 nodes: `vagrant up`
- SSH to node-01: `vagrant ssh node-01`
- Initialize swarm mode `sudo docker swarm init --advertise-addr 10.10.8.10` and copy the command for worker join
- SSH to node-01: `vagrant ssh node-02`
- Run swarm join command: `sudo docker swarm join --token <copy from swarm init output> 10.10.8.10:2377`
- SSH to node-01: `vagrant ssh node-03`
- Run swarm join command: `sudo docker swarm join --token <copy from swarm init output> 10.10.8.10:2377`
- Check cluster status: `sudo docker node ls`
- Explore service deployment etc: [link](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)
