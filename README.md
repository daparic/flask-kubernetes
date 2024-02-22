### Application Setup
The flask-kubernetes docker image must be built inside minikube
```
docker build -t flask-kubernetes . # to prepare the local docker image
```

and then from the outside, deploy to Kubernetes cluster:
```
kubectl apply -f deployment.yaml
minikube service flask-test-service
```

### Kubernetes Setup:
```
sudo apt update
sudo apt install curl apt-transport-https

wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
sudo chmod 755 /usr/local/bin/minikube
minikube version

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
sudo mv kubectl /usr/local/bin/kubectl
sudo chmod 755 /usr/local/bin/kubectl
kubectl version -o json

minikube start
```

### Kubernetes Commands:
```
kubectl config view
kubectl cluster-info
kubectl get nodes
kubectl get pod
kubectl get deployments
kubectl get deployments -n ns_smeagol
kubectl describe deployments
kubectl delete deployment smeagol
kubectl delete deployment smeagol --cascade

minikube ssh # go inside minikube and build flask-kubernetes inside
minikube status
minikube stop
minikube delete # delete single node cluster
minikube addons list
minikube dashboard
```

### Notes:
The local flask-kubernetes docker image must exists inside minikube. 
