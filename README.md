# Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) 
- npm 
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) 
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Docker](https://docs.docker.com/engine/install/ubuntu/)

## Navigate to the k8s Folder 
 `cd ~/yolo/k8s`

## run the neccessary yaml files on each separte directory : 

### database folder :
`kubectl apply -f mongo-statefulset.yaml`
`kubectl apply -f persistent-volume.yaml`
`kubectl apply -f persistent-volume-claim.yaml`

### application folder :
`kubectl apply -f backend.yaml & frontend.yaml`
`kubectl apply -f service-backend.yaml & service-frontend.yaml` 
`kubectl apply -f mongo-config.yaml & backend-config.yaml`

### nginx folder :
`kubectl apply -f nginx-config.yml`

### To check if pods are up and running use 
`kubectl get pods`

### To check if services are up and running use
`kubectl get services`

# DONE BY: 
Name: George Dekeijzer
Class: DEVOPS 03