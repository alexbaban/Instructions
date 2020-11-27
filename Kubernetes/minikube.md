# minikube
https://minikube.sigs.k8s.io/docs/
### minikube quickly sets up a local Kubernetes cluster on macOS, Linux, and Windows. 

`minikube start`  
`minikube dashboard`  
`kubectl get pods --all-namespaces`  

## Manage your cluster
`minikube stop` // halt the cluster  
`minikube delete --all` // delete all of the minikube clusters  
`minikube addons list` // browse the catalog of easily installed Kubernetes services  

## kubectl config
`kubectl config get-contexts` // displays list of contexts from the kubeconfig file  
`kubectl config use-context minikube` //switch between clusters  
`kubectl config current-context` // displays the current-context  

## Deploy applications

### Create a sample deployment
`kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4`  
`kubectl get deployments`  
`kubectl describe deployment hello-minikube`  

### Expose it on port 8080
`kubectl expose deployment hello-minikube --type=NodePort --port=8080` // 8080 is the port echoserver is listening on  
`kubectl get services`  
then  
`minikube service hello-minikube` // let minikube launch a web browser for you  
or  
`kubectl port-forward service/hello-minikube 7080:8080` // use kubectl to forward the port  
// application is now available at http://localhost:7080/
