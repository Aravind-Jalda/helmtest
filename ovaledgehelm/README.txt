Creating Ingress Controller: https://learn.microsoft.com/en-us/azure/aks/ingress-basic?tabs=azure-cli
-----------------------------------

NAMESPACE=ingress-basic

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx \
  --create-namespace \
  --namespace $NAMESPACE \
  --set controller.service.annotations."service\.beta\.kubernetes\.io/azure-load-balancer-health-probe-request-path"=/healthz

Creating Cert-manager: https://learn.microsoft.com/en-us/azure/aks/ingress-basic?tabs=azure-cli
-------------------------------------

kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.9.1/cert-manager.yaml


