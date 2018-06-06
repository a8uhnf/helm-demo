# helm-demo

### Required YAMLs

`req-yamls/` contains all the basic required yamls.

### Helm Install

For macOS
```
brew install kubernetes-helm
```

For Linux

- Download your [desired version](https://github.com/kubernetes/helm/releases)
- Unpack it (`tar -zxvf helm-v2.0.0-linux-amd64.tgz`)
- Find the `helm` binary in the unpacked directory, and move it to its desired destination (`mv linux-amd64/helm /usr/local/bin/helm`)

### Helm init into cluster

- `helm init`
- `helm list`
This leads us to RBAC error.
- `helm reset`.
 This leads us also to RBAC error too.
- `kc delete tiller-deploy -n kube-system`
this will delete the tiller from our cluster.
- `kc apply -f helm-install/helm-rbac.yaml`
this will install necessary rbac for helm with admin previlage.

### Back to Tutorial

1. `helm create <chart-name>`
2. `helm --dry-run --debug <chart-path>`
3. `helm install <chart-path>`
Optionally set values.
4. `helm repo add nginx-ingress https://kubernetes-charts-stable.storage.googleapis.com/`
// For dry-run
3. `helm install helm-1`