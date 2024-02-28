# argo-cd-demo
Test argo cd

After the cluster is set up, we need an ingress controller.

Steps (https://www.linode.com/docs/guides/deploy-nginx-ingress-on-lke/)

```
$ helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
$ helm repo update
$ helm install ingress-nginx ingress-nginx/ingress-nginx```
```

# Install cert manager CLI tool
(https://cert-manager.io/v1.0-docs/usage/kubectl-plugin/)

```
$ curl -L -o kubectl-cert-manager.tar.gz https://github.com/cert-manager/cert-manager/releases/download/v1.0.4/kubectl-cert_manager-linux-amd64.tar.gz
$ tar xzf kubectl-cert-manager.tar.gz
$ sudo mv kubectl-cert_manager /usr/local/bin
```