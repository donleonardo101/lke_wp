# kubernetes_lke1

https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

https://www.youtube.com/watch?v=JGtJj_nAA2s

cd ./secret

export KUBECONFIG=wplke-kubeconfig.yaml

echo $KUBECONFIG

dziala tylko w jednym panelu tilix

#kubectl get node

#https://helm.sh/docs/intro/install/

chmod 620 test-kubeconfig.yaml

helm repo add bitnami https://charts.bitnami.com/bitnami

#helm search repo bitnami

cd secret

#helm install mongodb --values ../test-mongodb.yaml bitnami/mongodb

kubectl get pod 

kubectl get all

kubectl get secret

#kubectl get secret mongodb -o yaml

#kubectl apply -f ../test-mongo-express.yaml

#

#helm repo add stable https://kubernetes-charts.storage.googleapis.com/ #nie

#helm repo add stable https://charts.helm.sh/stable/

#helm install nginx-ingress stable/nginx-ingress --set controller.publishService.enabled=true #nie

#helm uninstall nginx-ingress

#helm repo remove stable

#helm repo add nginx-stable https://helm.nginx.com/stable

#helm repo update

#helm install nginx-ingress nginx-stable/nginx-ingress --set controller.publishService.enabled=true #nie ma poda backend

#helm uninstall nginx-ingress

#helm repo remove nginx-stable
#

#helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

#helm repo update

#helm install wpk8s bitnami/wordpress --set allowOverrideNone=true

albo

helm install my-release \
  --set wordpressUsername=admin \
  --set wordpressPassword=password \
  --set mariadb.auth.rootPassword=secretpassword \
    bitnami/wordpress

#kubectl get svc --namespace default -w wpk8s

#echo Username: user

#echo Password: $(kubectl get secret --namespace default mollified-lynx-wordpress -o jsonpath="{.data.wordpress-password}" | base64 --decode)

#kubectl apply -f ../test-ingress.yaml

#Warning: extensions/v1beta1 Ingress is deprecated in v1.14+, unavailable in v1.22+; use networking.k8s.io/v1 Ingress

#kubectl scale --replicas=0 statefulset/mongodb

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

po testowaniu trzeba usunąc cluster, nodebalancer, vm, volumes na linode dashboard


skopiowac dane klastra z panelu linode do ~/.kube/config

https://www.pulumi.com/docs/tutorials/kubernetes/wordpress-chart/

https://github.com/pulumi/examples/tree/master/kubernetes-ts-helm-wordpress

trzeba skopiowac na piechote pliki z githuba

wget -O package.json https://raw.githubusercontent.com/pulumi/examples/master/kubernetes-ts-helm-wordpress/package.json

pulumi stack init 

pulumi up

curl -sL $(pulumi stack output frontendIp):80 | grep "<title>"

kubectl get secrets

login: user

kubectl get secrets/wpdev-wordpress -o json | jq '.data | map_values(@base64d)'


sprawdzic instalacje motywow i wtyczek i zapisywanie zdjec

usuwanie wp a potem trzeba recznie w panelu linode: 

pulumi destroy

koszt 0.21$ na poczatku

0.02 na godzine

730 godzin w miesiacu = 14.6$/miesiac = 57,67zł*12=692,04zł rocznie
