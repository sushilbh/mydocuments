## INSTALLING KUBERNETES

#### Installation of home-brew on Mac
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"



#### Installation of kubectl
1. curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
2. chmod +x ./kubectl
3. sudo mv ./kubectl /usr/local/bin/kubectl
4. kubectl version

NOTE: you will find below error because you don’t have setup k8s instance

* The connection to the server localhost:8080 was refused - did you specify the right host or port?


#### Installation of minikube
1.  brew install hyperkit
2. curl -LO https://storage.googleapis.com/minikube/releases/latest/docker-machine-driver-hyperkit \
&& sudo install -o root -g wheel -m 4755 docker-machine-driver-hyperkit /usr/local/bin/
3. brew cask install minikube
4. curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && sudo install minikube-darwin-amd64 /usr/local/bin/minikube
5. minikube start --vm-driver hyperkit
6. Minikube start


#### Uninstall minikube

minikube stop; minikube delete

#### minikube commands
* minikube start >>> start minikube
1. Kubectl proxy >>> open another terminal and execute <minikube dashboard> command it will open
2. Minikube dashboard >>>http://127.0.0.1:51863/api/v1/namespaces/kube-system/services/http:kubernetes-dashboard:/proxy/

* Minikube status >>> check status
* minikube stop >>> stop minikube
* kubectl get deployments >>> check deployments
* kubectl get pods >>> check pods
* kubectl delete deployment <deployment name> >>> delete deployments
* kubectl delete pods <pod name> >>> to delete pod
* kubectl get svc 
* kubectl logs <pod name>
* kubectl describe svc <pod name>
* kubectl apply -f <filename.yml>
* kubectl apply -f <github url>



