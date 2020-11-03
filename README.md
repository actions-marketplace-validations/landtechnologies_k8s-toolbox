# k8s toolbox

A selected group of tools for interacting with Kubernetes on an AWS environment. The action is made up of "composite steps" that install the tools onto the running build container.

## What's included?

1. `kubectl`
1. `kops`
1. `helm`
1. `render`
1. `aws-iam-authenticator`
1. `argo`

## How do I use it?

a) Explicitly specify any versions (or else they default to the latest release from each, found on GitHub)

```yaml
uses: landtechnologies/k8s-toolbox@v6
with:
  kubectl: "v1.18.10"
  kops: "v1.18.1"
  helm: "v3.3.4"
  argo: "v2.11.6"
  kube-config: ${{secrets.KUBE_CONFIG}}
```
b) Use a json file ([example](https://raw.githubusercontent.com/landtechnologies/docker-ci-images/master/version.json)) to specify the versions:

```yaml
uses: landtechnologies/k8s-toolbox@v6
with:
  versions: http://some.location.to.a.version.json.file
  kube-config: ${{secrets.KUBE_CONFIG}}
```

1. `kubectl`

   - defaults to the latest stable release on GitHub
   - `kube-config` is a base64 encoded copy of your `~/.kube/config` file, ie `base64 ~/.kube/config` stored in GitHub Secrets

   ```yaml
   uses: landtechnologies/k8s-toolbox@v6
   with:
     kubectl: "v1.18.10"
     kube-config: ${{secrets.KUBE_CONFIG}}
   ```

1. `kops`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: landtechnologies/k8s-toolbox@v6
   with:
     kops: "v1.18.0"
   ```

1. `helm`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: landtechnologies/k8s-toolbox@v6
   with:
     helm: "v3.3.4"
   ```

1. `argo`

   - defaults to the latest stable release on GitHub

   ```yaml
   uses: landtechnologies/k8s-toolbox@v6
   with:
     argo: "v2.11.6"
   ```
