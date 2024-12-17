Elastic Kubernetes Cluster  
Its a managed setup: AWS EKS does most of the thing.  

# Creating EKS cluster using CLI

[Installations of CLI tools](./Installing%20CLIs.md)

```shell
# create cluster
eksctl create cluster --name=<name> \
					  --region=<region> \
					  --zones=zone1,zone2 \
					  --without-nodegroup

# get list of clusters
eksctl get cluster
```

Create and associate IAM OIDC Provider for our cluster
```shell
eksctl utils associate-iam-oidc-provider \
	--region <region> \
	--cluster <clustername> \
	--approve
```

Create EC2 Keypair:
- AWS Console >> EC2 >> Keypairs (left hand menu) >> preferred .pem
- used when creating NodeGroup.
- helps login to Worker Nodes using cli.

Create Public NodeGroup:
```shell
eksctl create nodegroup --cluster=<clustername to attach to> \
						--region=<region> \
						--name=<nodegroup-name> \
						--node-type=<instance type> \
						--nodes=<count of nodes> \
						--nodes-min=<min nodes in ASG> \
						--nodes-max=<max nodes in ASG> \
						--node-volume-size=<size in GB> \
						--ssh-access \
						--ssh-public-key=<created keypair name> \
						--managed \
						--asg-access \ # IAM cluster-autoscaler policy
						--external-dnl-access \
						--full-ecr-access \
						--appmesh-access \
						--alb-ingress-access
```

Verify:
```shell
# get clusters
eksctl get cluster

# get nodes
kubectl get nodes -o wide

# list nodegroups in a cluster
eksctl get nodegroup --cluster=<clustername>

# view config
kubectl config view --minify

# ssh into ndoes using keypair
ssh -i keypair.pem user@ip-address-of-node
```

Delete the cluster:
```shell
# delete nodegroup
eksctl delete nodegroup --cluster=<clustername> --name=<nodegroup-name>

# delete cluster
eksctl delete cluster <clustername>
```