# Environment Variables
Environment variables are a set of dynamic named values that can affect the way running processes will behave on a computer.

On Kubernetes, environment variables are often used to configure applications running in a Pod. This is done by setting the environment variables in the Pod specification.

In this lesson, we will learn how to set environment variables in a Pod.

## ENV Value Types
Environment variables can be set to different types of values. The most common types are:

- **Plain Key Value**: A simple key-value pair.
  Example:
  ```yaml
  env:
    - name: MY_VAR
      value: my-value
  ```
- **ConfigMap**: A value stored in a Kubernetes ConfigMap.
  Example:
  ```yaml
  env:
    - name: MY_VAR
      valueFrom:
        configMapKeyRef:
          name: my-configmap
          key: MY_VAR
  ```
- **Secret**: A value stored in a Kubernetes Secret.
  Example:
  ```yaml
  env:
    - name: MY_VAR
      valueFrom:
        secretKeyRef:
  ```