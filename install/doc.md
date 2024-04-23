sudo helm package harbor/
rm -f ./harbor-1.14.2.tgz
sudo helm install harbor ./harbor-1.14.2.tgz -f install/values.yaml

sudo helm uninstall harbor

sudo helm upgrade harbor ./harbor-1.14.2.tgz --set expose.type=loadBalancer,expose.tls.certSource=none

echo "SGFyYm9yMTIzNDU=" | base64 -d

echo -n "Harbor12345UleyanQlma3vTRHXrEVfAxPI3eyrWrv4" | sha256sum

sudo helm upgrade harbor ./harbor-1.14.2.tgz -f install/values.yaml

sudo kubectl create namespace harbor-system
sudo kubectl label namespace harbor-system istio-injection=enabled
sudo kubectl label namespace harbor-system istio-injection-

sudo helm upgrade harbor ./harbor-1.14.2.tgz -f install/values.yaml -n harbor-system --wait