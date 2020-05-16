# kubernetes-configmap-reload

Pre-requisites:
--------
    - Install Git
    - Install Maven
    - Install Docker
    - EKS Cluster
    
Clone code from github:
-------
    git clone https://github.com/VamsiTechTuts/spring-cloud-kubernetes.git
    cd spring-cloud-kubernetes
    
Build Maven Artifact:
-------
    mvn clean install
 
Build Docker image for Springboot Application
--------------
    docker build -t vamsitechtuts/kubernetes-configmap-reload .
  
Docker login
-------------
    docker login
    
Push docker image to dockerhub
-----------
    docker push vamsitechtuts/kubernetes-configmap-reload
    
Deploy Spring Application:
--------
    kubectl apply -f kubernetes-configmap.yml
    
Check Deployments, Pods and Services:
-------

    kubectl get deploy
    kubectl get pods
    kubectl get svc
    
Now Goto Loadbalancer and check whether service comes Inservice or not, If it comes Inservice copy DNS Name of Loadbalancer and Give in WebUI

    http://a70a89c22e06f49f3ba2b3270e974e29-1311314938.us-west-2.elb.amazonaws.com:8080/home/data
