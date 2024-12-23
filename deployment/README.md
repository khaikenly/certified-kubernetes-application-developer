# Template for creating a Kubernetes Deployment

## Description
- Deployment is a Kubernetes controller that manages a replicated application.
- It creates Pods and ReplicaSets to ensure the desired number of Pods are running at any given time.

## Definition
- Deployment is defined using a YAML file.
- Below is a sample YAML file for creating a Deployment.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
  labels:
    app: myapp-deployment
spec:
    replicas: [number_of_replicas]
    selector: // Selects the pods to manage using the labels defined in the template below
        matchLabels:
            app: myapp-pod
    template:
        metadata:
            name: my-pod
            labels:
                app: myapp-pod
        spec:
            containers:
            - name: my-container
                image: nginx
```