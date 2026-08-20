# helm install
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
helm version

# Add to the heml
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

# install the ingress controller
helm install ingress-nginx ingress-nginx/ingress-nginx \
  --namespace ingress-nginx \
  --create-namespace

kubectl get pods -n ingress-nginx