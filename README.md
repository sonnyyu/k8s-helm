# k8s-helm
```sh
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
chmod go-r ~/.kube/config
helm version
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
wait few minutes
curl http://192.168.1.3
helm list --all
helm delete my-apache
helm list --all
```
