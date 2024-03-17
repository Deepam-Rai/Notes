Official doc: https://kubernetes.io/docs/reference/kubectl/  

## Commonly used commands:  

| **Command** | **Purpose** |
| ---- | ---- |
| `minikube start` | Create minikube cluster |
| `minikube dashboard` | Launch a browser to view dashboard |
| `kubectl create deployment ...` | Deploy app |
| `kubectl get deployments` | View the deployments |
| `kubectl get pods` | View the pods |
| `kubectl get events` | View the events |
| `kubectl config view` | View the configs |
| `kubectl logs <name>` | View application logs for a container in pod |
| `kubectl expose deployment <deployment name> --type=LoadBalancer --port=<port>` | Expose pod to public internet as a service |
| `kubectl get services` | View the services created |
| `minikube service <deployment name>` | Service the local deployment by minikube to make it accessible via a browser |
| `minikube addons list` | List currently supported addons |
| `minikube addons enable <addons>` | Enable addons |
| `minikube addons disable <addons>` | Disable addons |
| `kubectl get pods,svc -n kube-system` | Retrieve info about pods and services within namespace `kube-system` |
| `kubectl top pods` | View the metrics of pods. (needs `metrics-server` enabled) |
| `kubectl delete service <name>` | Delete deployed service |
| `kubectl delete deployment <deployment name>` | Delete deployment |
| `minikube stop` | Stop minikube cluster |
| `minikube delete` | Delete the minikube VM |


Others:

|  |  |
| ---- | ---- |
| `kubectl get pods -o wide` | Show IP, Gates etc. |
| `kubectl describe svc <service name>` | Description of the services. |
