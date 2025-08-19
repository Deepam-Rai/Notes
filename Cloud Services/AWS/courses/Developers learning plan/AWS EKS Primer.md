>**AWS Elastic Kubernetes Service (EKS):** is a managed container orchestration service that facilitates deploying, managing and scaling of Kubernetes applications in the AWS cloud or on premises.


# Kubernetes concepts

Kubernetes objects:
- **Cluster**: A set of worker machines, called nodes, that run containerized applications.
- **Node**: A virtual or physical machine.
- **Pod**: A group of one or more containers.
- **Ephemeral volume**: Shared volume to facilitate data sharing in the pod and persistence of data across container restarts. Destroyed when pod ceases to exist.
- **Persistent volume**: Shared volume that facilitates data sharing across containers and has lifecycle independent of containers or pods.
- **Service:** Logical collection of pods and means to access them.
- **Namespace**: Virtual cluster backed by the same physical cluster.
- **ReplicaSet**: Ensures that a specific number of pod replicas are running at any given time.
- **Deployment**: Owns and manages ReplicaSets or individual pods.
- **ConfigMap**: An API object that stores non-confidential data as key-value pairs used by other Kubernetes objects.
- **Secrets**: Stores confidential data.

>**Control Plane**: Control plane nodes manage the worker nodes and the pods in the cluster.

>**Data Plane**: Worker nodes hosts the pods that are components of the application workload.

# EKS Control Plane
- Amazon EKS manages the Kubernetes control plane
- **Amazon EKS API** `eksctl`: Used for anything that is managed by Amazon EKS i.e., entire Control Plane and possibly parts of data plane via managed node groups and Fargate.
- **Kubernetes API** `kubectl`: Used for managing Kubernetes objects.

# Preparing AWS Environment

## Configuring Permissions
1. **Cluster IAM Role**: For EKS to make calls to AWS APIs to manage the cluster.
2. **Node IAM Role**: For `kubelet` daemon on EKS worker nodes make calls to AWS APIs.
3. **RBAC User**: For administrators managing cluster to make calls to Kubernetes API. Done by mapping IAM roles to a Kubernetes RBAC user.

## Configuring Network
Amazon EKS networking requirements for VPC and subnets: https://docs.aws.amazon.com/eks/latest/userguide/network-reqs.html

## Creating Cluster
(Deploying Amazon EKS managed Control Plane)

Methods:
1. `eksctl`: Command line tool that automates many steps. Can be declarative (YAML) or imperative.
2. Management console: GUI but some steps needs to be done with AWS CLI.
3. AWS CLI: Most complex and most customizable.

## Configuring scaling
>**Horizontal scaling/Scale out:** Adding/removing more compute resources.

>**Vertical scaling/Scale up**: Add more resource to the computer resource.

Kubernetes auto-scaling:
1. Cluster Autoscaler (CA): Scales the number of nodes in or out.
	1. Done by adding worker nodes to EC2 Auto Scaling groups.
	2. Alternative: Karpenter.
2. Horizontal Pod Autoscaler (HPA): Scales number of pods in or out.
3. Veritcal Pod Autoscaler (VPA): Scales resources available to pods up or down.

```shell
watch "kubectl get nodes; echo; kubectl get hpa, pods -o wide"
```

## Manging communication
To simplify inter-node communication, Amazon EKS integrates Amazon VPC into Kubernetes through Amazon VPC Container Network Interface (CNI) plugin for Kubernetes. This allows pods to have the same IP address as they do on the VPC network.

## Managing storage in Amazon EKS
Kubernetes objects:
2. Persistent Volume: Storage with lifecycle independent of pods.
3. Persistent Volume Claim (PVC): Request for storage by a cluster user. Includes details for kind of storage desired.
4. Storage classes: Automates persistent volume management within Kubernetes cluster.

Container Storage Interface (CSI): Driver to allow Kubernetes cluster access to desired storage provider.  
- Amazon EBS and EFS have their respective CSI drivers that runs as containerized applications in the cluster. Makes required AWS API calls on behalf of storage class object.

```shell
kubectl get pv, all -A;
```

## Deploying applications
 `kubectl` has high administrative overhead and not suitable for scalability just by itself, thus for CI/CD combination of Helm, Github actions, etc are used.

## Deploying service mesh with AWS App Mesh
>**AWS App Mesh:** is a service mesh that provides application level networking to help services communicate with each other across multiple types of computing infrastructure.

- dedicated infrastructure layer that abstracts away service-to-service communication.

## Maintaining add-ons
Amazon EKS automatically adds following add-ons:
- Amazon VPC CNI
- kube-proxy
- CoreDNS
