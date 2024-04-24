sudo helm package ory/helm/charts
rm -f ./harbor-1.14.2.tgz
sudo helm install harbor ./harbor-1.14.2.tgz -f install/values.yaml