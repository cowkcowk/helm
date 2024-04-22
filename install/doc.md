helm package harbor/
sudo helm install harbor ./harbor-1.14.2.tgz -f install/values.yaml

sudo helm upgrade harbor ./harbor-1.14.2.tgz --set expose.type=loadBalancer,expose.tls.certSource=none

echo "SGFyYm9yMTIzNDU=" | base64 -d

echo -n "Harbor12345UleyanQlma3vTRHXrEVfAxPI3eyrWrv4" | sha256sum

sudo helm upgrade harbor ./harbor-1.14.2.tgz -f install/values.yaml