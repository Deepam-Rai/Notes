>**Swarm mode:** is an advanced feature for managing a cluster of docker engines.

- Can modify service's configuration, including networks and volumes, without manually restarting the containers. Docker stops the old service tasks, updates configuration, starts new service task automatically.
- Standalone docker containers can be run on the hosts participating in docker swarm.

----
# Key concepts
## Services and tasks
> **Service:** is the definition of the task to be executed on a nodes.

- Once a task is assigned to a node, it cannot be moved to another node

----
# Architecture
![docker swarm](Images/Docker/docker_swarm.png)

## Nodes
> **Node:** is an instance of docker engine participating in the swarm.

Each node in the cluster can be of two types(or both):
1. Manager nodes
2. Worker nodes

![docker swarm](Images/Docker/docker_swarm_nodes.webp)

Node availability states:
1. `drain`: gracefully stops scheduling tasks on these node
2. `active`: the node is capable of handling tasks
Nodes can be promoted and demoted to each other.  
### Manager nodes
Responsible for:
1. Maintaining cluster state: uses Raft implementation to maintain consistent state of entire swarm.
2. Scheduling services
3. Serving swarm mode HTTP API endpoints

By default all manager are also workers.

### Worker nodes
1. Executor nodes.

## Load balancing
The swarm manager uses ingress load balancing to expose the services that is to be made available externally to the swarm.  

