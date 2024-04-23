sudo helm repo add istio https://istio-release.storage.googleapis.com/charts
sudo helm repo update
sudo helm search repo istio


sudo kubectl create namespace istio-system
sudo helm install istio-base istio/base -n istio-system --set defaultRevision=default

sudo helm install istiod istio/istiod -n istio-system --wait
sudo helm status istiod -n istio-system

sudo kubectl create namespace istio-ingress
sudo helm install istio-ingress istio/gateway -n istio-ingress --wait
sudo helm install istio-ingressgateway istio/gateway -n istio-ingress --wait
sudo helm ls -n istio-system
sudo helm ls -n istio-ingress
sudo helm status istio-ingress -n istio-ingress

sudo helm status istio-ingressgateway
sudo helm get all istio-ingressgateway

# update config

sudo helm show values istio/gateway

# Delete

sudo helm delete istio-ingress -n istio-ingress
sudo kubectl delete namespace istio-ingress
sudo helm delete istiod -n istio-system
sudo helm delete istio-base -n istio-system
sudo kubectl delete namespace istio-system

sudo kubectl get crd -oname | grep --color=never 'istio.io' | xargs sudo kubectl delete


sudo kubectl label namespace default istio-injection=enabled
sudo kubectl label namespace default istio-injection-