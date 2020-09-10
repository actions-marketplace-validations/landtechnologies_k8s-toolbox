# k8s toolbox

A selected group of tools for interacting with Kubernetes. "Composite steps" that install the tools onto the running build container.

## What's included?

1. `kubectl` 
1. `helm`
1. `render`
1. `aws-iam-authenticator`
1. `argo`

## How do I use it?

1. `kubectl`
    
    - defaults to `v1.18.0`
    - `kube-config` is a base64 encoded copy of your `~/.kube/config` file, ie `base64 ~/.kube/config` stored in GitHub Secrets

    ```yaml
    uses: robertbeal/k8s-toolbox@v7
    with:
        kubectl: "v1.17.0"
        kube-config: ${{secrets.KUBE_CONFIG}}
    ```
