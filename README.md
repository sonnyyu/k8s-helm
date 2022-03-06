# k8s-helm

# Get Install Software
```sh
git clone https://github.com/sonnyyu/k8s-helm
cd k8s-helm
```
# Install Helm
```sh
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
chmod go-r ~/.kube/config
helm version
```
# Edit values.yaml
```sh
nano values.yaml
addresses:
# Replace with idle IP in the same subnet as the node IP.
- 192.168.1.3-192.168.1.4
```
# Install metallb
```sh
# Add the Helm repository:
$ helm repo add bitnami https://charts.bitnami.com/bitnami
# Update your local Helm chart repository cache:
$ helm repo update
# crate namespace:
$ kubectl create namespace metallb-system
# To install Helm chart:
$ helm install metallb bitnami/metallb --namespace metallb-system -f values.yaml
```
# Install nginx
```sh
# To install nginx
helm install my-nginx bitnami/nginx
# Get nginx pod
kubectl get pods --all-namespaces |grep my-nginx
# Get Service
kubectl get service -o wide  --all-namespaces
#test nginx
curl http://192.168.1.3
```
# Install app by helm
```sh
helm repo list
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add default https://charts.helm.sh/stable
helm repo list
helm repo update
helm search repo nginx
helm install my-nginx bitnami/nginx
kubectl get pods --all-namespaces
kubectl get service -o wide 
curl http://192.168.1.3
helm list --all
helm delete my-nginx
helm list --all
helm search repo apache
helm install my-apache bitnami/apache
kubectl get service -o wide 
kubectl get pods --all-namespaces  |grep my-apache
#wait few minutes
curl http://192.168.1.3
helm list --all
helm delete my-apache
helm list --all
```
