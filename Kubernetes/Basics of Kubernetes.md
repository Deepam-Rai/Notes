# [Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)

> Kubernetes is an open-source orchestration system for automating software deployment, scaling and management.

- Abstracts the deployed application via containerization, making them independent of any specific host machine.
# Cluster
Consists of resources:
1. **Control pane:** coordinates the cluster.
2. **Nodes**: worker units that run the applications.
	1. is a VM.
	2. each has **Kubelet** that manages the node and communicates with control pane using Kubernetes API.


----
# Practice in localhost

## Minikube
Minikube is lightweight implementation of kubernetes that creates VM on local machine and deploys a simple cluster.
## [Hello Minikube](https://kubernetes.io/docs/tutorials/hello-minikube/)

Tutorial: https://kubernetes.io/docs/tutorials/hello-minikube/  

During kubectl  setup, adding `kubectl` to the path guide: https://core.digit.org/guides/operations-guide/working-with-kubernetes/installation-of-kubectl  

----
