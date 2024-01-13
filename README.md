# Overview
A TeKanAid Academy Playground to practice Kubernetes skills.

## Instructions

1. You will get access to a Linux terminal with `kubectl`, `helm`, `k9s`, `kubectx`, and `kubens` already installed.
2. A Minikube instance will automatically start, this takes about 5 minutes so please be patient!
3. I've also included a list of aliases to use:
- alias k="kubectl"
- alias kga="kubectl get all"
- alias kgn="kubectl get all --all-namespaces"
- alias kdel="kubectl delete"
- alias kd="kubectl describe"
- alias kg="kubectl get"

### Repository for the K8s in 1 hour video

#### K8s manifest files 
* mongo-config.yaml
* mongo-secret.yaml
* mongo.yaml
* webapp.yaml

#### K8s commands

##### start Minikube and check status
    minikube start --vm-driver=hyperkit 
    minikube status

##### get minikube node's ip address
    minikube ip

##### get basic info about k8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

##### get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

##### get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs
    kubectl logs {pod-name}

##### stop your Minikube cluster
    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />

#### Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour

#### Steps
    minikube status
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all
    kubectl get pod -o wide
    kubectl get node -o wide
    kubectl apply -f mongo-config.yaml
    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f webapp.yaml
    kubectl get all
    kubectl get configmap
    kubectl get secret
    kubectl describe service webapp-service
    kubectl describe pod webapp-deployment-5db75479c6-w5tdr(copy from above)
    kubectl get pods
    kubectl logs
    kubectl logs webapp-deployment-5db75479c6-w5tdr
    kubectl get svc
    minikube ip
    kubectl get node -o wide
    INTERNAL-IP:PortNumber
