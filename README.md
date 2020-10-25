# k8s toolbox

A selected group of tools for interacting with Kubernetes. The action is made up of "composite steps" that install the tools onto the running build container.

## What's included?

1. `kubectl`
1. `kops`
1. `helm`
1. `render`
1. `aws-iam-authenticator`
1. `argo`

## How do I use it?

tldr;

```yaml
uses: robertbeal/k8s-toolbox@v13
with:
  kubectl: "v1.18.10"
  kops: "v1.18.1"
  helm: "v3.3.4"
  argo: "v2.11.6"
  kube-config: ${{secrets.KUBE_CONFIG}}
```

1. `kubectl`

   - defaults to the latest stable release on GitHub
   - `kube-config` is a base64 encoded copy of your `~/.kube/config` file, ie `base64 ~/.kube/config` stored in GitHub Secrets

   ```yaml
   uses: robertbeal/k8s-toolbox@v13
   with:
     kubectl: "v1.18.0"
     kube-config: ${{secrets.KUBE_CONFIG}}
   ```

1. `kops`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: robertbeal/k8s-toolbox@v13
   with:
     kops: "v1.18.0"
   ```

1. `helm`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: robertbeal/k8s-toolbox@v13
   with:
     helm: "v3.3.4"
   ```

1. `argo`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: robertbeal/k8s-toolbox@v13
   with:
     argo: "v2.11.6"
   ```
