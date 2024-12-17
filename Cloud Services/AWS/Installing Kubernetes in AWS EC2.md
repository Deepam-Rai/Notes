
# Using Kubeadm
Reference: Installing Kubernetes on AWS EC2 Instance using Kubeadm under 10 mins | EKS Masterclass with Demos: https://youtu.be/mpYGydGuH3E?si=wS_v1EbCrIZ68XmV

1. Create two AWS EC2 instances (ubuntu): master node and worker node.
2. Connect to master node and install kubeadm:
```shell
# need sudo
sudo su -;

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl";

# initialize Kubernetes master node
sudo kubeadm config images pull

sudo kubeadm init

mkdir -p "$HOME"/.kube
sudo cp -i /etc/kubernetes/admin.conf "$HOME"/.kube/config
sudo chown "$(id -u)":"$(id -g)" "$HOME"/.kube/config

 # Network Plugin = calico
kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.0/manifests/calico.yaml

# generate token for worker nodes to join
kubeadm token create --print-join-command
# this command will be required to be run in worker node
```
3. Expose port `6443` in Security group, for worker node to connect to master node.
	1. instance >> Security >> Inbound rules >> Edit inbound rule >> 
4. Connect to worker node and install kubeadm:
```shell
# need sudo
sudo su -;

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl";

sudo kubeadm reset pre-flight checks;

# run the command got from master node with `--v=5` added at the end
kubeadm join ... --v=5;
```
5. Verify that worker-node is connected by running `kubectl get nodes` at master-node.