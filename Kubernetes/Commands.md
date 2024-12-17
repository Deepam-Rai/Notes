Official doc: https://kubernetes.io/docs/reference/kubectl/  

## Commonly used imperative commands:  

| **Command**                                                                     | **Purpose**                                                                  |
| ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `minikube start`                                                                | Create minikube cluster                                                      |
| `minikube dashboard`                                                            | Launch a browser to view dashboard                                           |
| `kubectl create deployment ...`                                                 | Deploy app                                                                   |
| `kubectl get deployments`                                                       | View the deployments                                                         |
| `kubectl run <podname> --image=<image>`                                         | Run a new pod.                                                               |
| `kubectl get pods`                                                              | View the pods                                                                |
| `kubectl get pods -o wide`                                                      | Show IP, Gates etc.                                                          |
| `kubectl exec -it <podname> -- bash`                                            | Run commands inside a pod. `-it` for interactive                             |
| `kubectl delete pod/<podname> --now`                                            | Delete pod                                                                   |
| `kubectl describe pod/<podname>`                                                | Description of the pod                                                       |
| `kubectl logs <name>`                                                           | View application logs for a container in pod                                 |
| `kubcetl logs pod/<podname> -c <container>`                                     | Logs of specific container in a pod                                          |
| `kubectl get events`                                                            | View the events                                                              |
| `kubectl config view`                                                           | View the configs                                                             |
| `kubectl expose deployment <deployment name> --type=LoadBalancer --port=<port>` | Expose pod to public internet as a service                                   |
| `kubectl get services`                                                          | View the services created                                                    |
| `minikube service <deployment name>`                                            | Service the local deployment by minikube to make it accessible via a browser |
| `minikube addons list`                                                          | List currently supported addons                                              |
| `minikube addons enable <addons>`                                               | Enable addons                                                                |
| `minikube addons disable <addons>`                                              | Disable addons                                                               |
| `kubectl get pods,svc -n kube-system`                                           | Retrieve info about pods and services within namespace `kube-system`         |
| `kubectl top pods`                                                              | View the metrics of pods. (needs `metrics-server` enabled)                   |
| `kubectl delete service <name>`                                                 | Delete deployed service                                                      |
| `kubectl delete deployment <deployment name>`                                   | Delete deployment                                                            |
| `minikube stop`                                                                 | Stop minikube cluster                                                        |
| `minikube delete`                                                               | Delete the minikube VM                                                       |
| `kubectl describe svc <service name>`                                           | Description of the services                                                  |


## Declarative approach

Creating and using yaml manifest file:
```shell
# create manifest file
kubectl run <podname> --image=<image> --dry-run=client -o yaml sleep infinity | tee <manifest_file.yaml>

# get description of manifest file elements
kubectl explain <kind>.<element>.<hierarchy>
# e.g.: kubectl explain pod.spec.restartPolicy

# creating pod using manifest file
kubectl create -f <manifest_file.yaml>

# applying changes; also creates of pod doesn't exist
kubectl apply -f <manifest_file.yaml>

# combining manifest files for multiple pods
{ cat manifest1.yaml; echo "---"; cat manifest2.yaml } | tee manifest.yaml
```
