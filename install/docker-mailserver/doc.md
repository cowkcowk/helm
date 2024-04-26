sudo helm package docker-mailserver/
rm -f ./docker-mailserver-3.0.9.tgz
sudo helm install mailserver ./docker-mailserver-3.0.9.tgz -f install/docker-mailserver/values.yaml
sudo helm upgrade mailserver ./docker-mailserver-3.0.9.tgz -f install/docker-mailserver/values.yaml
sudo helm uninstall mailserver