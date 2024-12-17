> **Pod:** A smallest unit of compute

- Host one or more containers.
- Containers in a pod can communicate using IPC (Inter Process Communication)
- A pod can encapsulate application, its dependencies, shared storage, networking into a single deployable unit.
- Each pod is assigned a unique IP address within the cluster.
- Pods can interact with each other using assigned IP addresses.

----
Commands: [Commands](./Commands.md)


----
# scripts

Get pod IP address in env var:
```shell
POD_IP=$( kubectl get pods -o wide | awk ' /<podname>/ { print $6 }');
echo $POD_IP;
```

Run a new pod and put into sleep:
```shell
kubectl <podname> --image=<image> --env"ENV_VAR=$EXISTING_VAR" -- sleep infinity
```

