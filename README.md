### argo-cd-demo
Test argo cd

After the cluster is set up, we need an ingress controller.

Steps (https://www.linode.com/docs/guides/deploy-nginx-ingress-on-lke/)

```
$ helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
$ helm repo update
$ helm install ingress-nginx ingress-nginx/ingress-nginx```
```

### Install cert manager CLI tool
(https://cert-manager.io/v1.0-docs/usage/kubectl-plugin/)

```
$ curl -L -o kubectl-cert-manager.tar.gz https://github.com/cert-manager/cert-manager/releases/download/v1.0.4/kubectl-cert_manager-linux-amd64.tar.gz
$ tar xzf kubectl-cert-manager.tar.gz
$ sudo mv kubectl-cert_manager /usr/local/bin
```

### Make our cluster to be able to connect to private docker registry

!!! IMPORTANT !!!

The `imagePullSecret` can only reference Secret within the same namespace. More about the topic [link](https://stackoverflow.com/a/76210102/15647017).

```
kubectl create secret docker-registry myregistrykey --docker-server=DOCKER_REGISTRY_SERVER --docker-username=DOCKER_USER --docker-password=DOCKER_PASSWORD --docker-email=DOCKER_EMAIL
```

### Configure to use the same load balancer


To retrieve the ID of the available load balancers and subsequently reuse the same load balancer across different services.

`linode-cli nodebalancers list`

`kubectl describe ingress argocd-ingress -n argocd`

`kubectl --namespace ingress-nginx get services -o wide -w ingress-nginx-controller`