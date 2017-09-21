# KubernetesWorkshop
Code for deploying a sample application to Kubernetes

#Create New Deployment
kubectl create -f local-volume.yml
kubectl create secret generic postgres-pass --from-file=password
kubectl create -f postgres.yml
kubectl create -f contacts-api.yml
kubectl create -f contacts-ui.yml

#Rolling update the deployment
kubectl rolling-update <EXISTING RC NAME> -f contacts-api.yml 
kubectl rolling-update <EXISTING RC NAME> -f contacts-ui.yml 