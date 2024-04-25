sudo helm package ory/helm/charts/kratos
rm -f ./harbor-1.14.2.tgz
sudo helm install kratos ./kratos-0.41.0.tgz -f install/ory/kratos/values.yaml

sudo helm uninstall kratos