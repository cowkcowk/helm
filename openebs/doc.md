helm repo add openebs https://openebs.github.io/openebs
helm repo update

sudo helm install openebs --namespace openebs openebs/openebs --create-namespace

sudo helm install openebs --namespace openebs openebs/openebs --set engines.replicated.mayastor.enabled=false --create-namespace

sudo helm uninstall openebs --namespace openebs