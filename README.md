# kubernetes_lke1

https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

https://www.youtube.com/watch?v=JGtJj_nAA2s

cd ./secret
export KUBECONFIG=wplke-kubeconfig.yaml

echo $KUBECONFIG

dziala tylko w jednym panelu tilix

kubectl get node

#https://helm.sh/docs/intro/install/

chmod 620 test-kubeconfig.yaml

helm repo add bitnami https://charts.bitnami.com/bitnami

helm search repo bitnami

cd sekret

#helm install mongodb --values ../test-mongodb.yaml bitnami/mongodb

kubectl get pod 

kubectl get all

kubectl get secret

#kubectl get secret mongodb -o yaml

#kubectl apply -f ../test-mongo-express.yaml

#<<<<<<<<<<<<<<<<>>>>>>>>>>>>>>>>
helm repo add stable https://kubernetes-charts.storage.googleapis.com/ #nie

helm repo add stable https://charts.helm.sh/stable/

helm install nginx-ingress stable/nginx-ingress --set controller.publishService.enabled=true #nie

helm uninstall nginx-ingress

helm repo remove stable

helm repo add nginx-stable https://helm.nginx.com/stable

helm repo update

helm install nginx-ingress nginx-stable/nginx-ingress --set controller.publishService.enabled=true #nie ma poda backend

helm uninstall nginx-ingress

helm repo remove nginx-stable
#<<<<<<<<<<<<<<<<<<<<<<<<<<>>>>>>>>>>>>>>>>>>>>>>>>>>
#helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm repo update

helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true

kubectl get svc

#kubectl apply -f ../test-ingress.yaml

#Warning: extensions/v1beta1 Ingress is deprecated in v1.14+, unavailable in v1.22+; use networking.k8s.io/v1 Ingress

#kubectl scale --replicas=0 statefulset/mongodb

delete cluster, nodebalancer, vms, volumes in linode dashboard
