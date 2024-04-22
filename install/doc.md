helm package harbor/
sudo helm install harbor ./harbor-1.14.2.tgz -f install/values.yaml

sudo helm upgrade harbor ./harbor-1.14.2.tgz --set expose.type=loadBalancer,expose.tls.certSource=none