# argo-cd-demo
Test argo cd

After the cluster is set up, we need an ingress controller.

Steps (https://www.linode.com/docs/guides/deploy-nginx-ingress-on-lke/)

`helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx`

`helm repo update`

`helm install ingress-nginx ingress-nginx/ingress-nginx`

