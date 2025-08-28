# Pull image with secret

When you want to **pull an image** from a **private registry**, you need to **provide the credentials** to **authenticate** with the **registry**. Therefore, you need to **create a secret** that contains the credentials and then use that secret to pull the image.

### Step 1: Create registry secret

You can use either one to create registry secret:

- [Imperative way to create registry secret](../env-and-secrets-setup/#imperative_1)
- [Declarative way to create registry secret](../env-and-secrets-setup/#docker-config)

### Step 2: Apply secret to pod

```yaml title="pod.yaml"
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  imagePullSecrets:
    - name: my-secret # secret name
  containers:
    - name: my-container
      image: my-image
```
