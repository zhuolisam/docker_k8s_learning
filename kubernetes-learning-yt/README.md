### K8s in 1 hour video Tutorial

This is a tutorial repository from the video Kubernetes Crash Course for Absolute Beginners by TechWorld with Nana.

Watch the tutorial here - [Kubernetes Crash Course for Absolute Beginners](https://www.youtube.com/watch?v=s_o8dwzRlu4)

#### K8s manifest files 
* mongo-config.yaml
* mongo-secret.yaml
* mongo.yaml
* webapp.yaml

#### K8s commands

##### start Minikube and check status
For me, I used docker as vm driver

    minikube start --vm-driver=hyperkit
    minikube start --driver docker
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
    kubectl logs {pod-name} -f #to stream the logs
    
##### stop your Minikube cluster
    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

> :warning: **If you are using Docker as Driver** 

If you're using Docker and the Minikube IP can't be reached, execute the following command:
    
    minikube tunnel
    minikube service webapp-service --url

The last line will give you the corerct IP and port

<br />

#### Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour

