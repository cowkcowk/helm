sudo helm package docker-mailserver/
rm -f ./docker-mailserver-3.0.9.tgz
sudo helm install cowk8s ./docker-mailserver-3.0.9.tgz -f install/docker-mailserver/values.yaml --namespace mail --create-namespace
sudo helm upgrade cowk8s ./docker-mailserver-3.0.9.tgz -f install/docker-mailserver/values.yaml -n mail
sudo helm uninstall mailserver

sudo kubectl exec -it --namespace mail deploy/cowk8s -- bash

setup email add phantantai@cowk8s.com password

sudo kubectl exec -it --namespace mail deploy/cowk8s-docker-mailserver -- setup email add phantantai@cowk8s.com password