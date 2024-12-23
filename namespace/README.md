# Template for creating a Kubernetes Namespace

## Description
- Namespace is a way to divide cluster resources between multiple users.
- It is used to create virtual clusters within the same physical cluster.

## Definition
- Namespace is defined using a YAML file.
- Below is a sample YAML file for creating a Namespace.

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: my-namespace
```

## Usage
- Create a Namespace using the below command.

```bash
kubectl apply -f namespace.yaml
```

## Resrouces quouta for Namespace
- Resource quota is a way to limit the amount of resources that can be used by a namespace.

## Definition
- Resource quota is defined using a YAML file.
- Below is a sample YAML file for creating a Resource Quota.

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: my-resource-quota
  namespace: my-namespace
spec:
  hard:
    pods: "10"
    requests.cpu: "4"
    requests.memory: 4Gi
    limits.cpu: "10"
    limits.memory: 10Gi
```

- You can set resource quota for a namespace using the below command.

```bash
kubectl apply -f resource-quota.yaml
```