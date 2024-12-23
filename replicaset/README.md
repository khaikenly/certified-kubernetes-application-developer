# Template for creating a Kubernetes ReplicaSet

## Description
- ReplicaSet is a Kubernetes controller that ensures a specified number of pod replicas are running at any given time.

## Definition
- ReplicaSet is defined using a YAML file.
- Below is a sample YAML file for creating a ReplicaSet.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: my-replicaset
  labels:
    app: myapp-replicaset
spec:
    replicas: [number_of_replicas]
    selector: // Selects the pods to manage using the labels defined in the template below
        matchLabels:
            app: myapp-pod
    template:
        [pod_template]
        name: my-pod
        labels:
            app: myapp-pod
        spec:
            containers:
            - name: my-container
              image: nginx
```