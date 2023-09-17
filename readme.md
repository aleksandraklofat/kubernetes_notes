# Notes about kubernetes

# Major commands

kubectl run hello-mini-kube <br/>
kubectl cluster-info</br>
kubectl get nodes<br/>

# Kubernetes - Parts

Scheduler - responsible for distributing work or containers across multiple nodes.<br/>

container runtime - the underlying framework that is responsible for running application in containers like Docker <br/>

kubectl - command line utility used to manage a kubernetes cluster,
it deploys a docker container by creating a pod <br/>

etcd -  a distributed reliable key-value store used by kubernetes to store all data used to manage the cluster <br/>


# Kubernetes Pods

We have Docker images and they are present on Docker Hub. Kubernetes CLuster is set up. 

Ziel/ Task: Deploy an application in a form of containers in a set of machines. 
Containers are encapsulated into a cubernetes object known as pod. 

Pod = single instance of application /smallest object that you can create in kubernetes. 
When we are scaling an apllication we are creating new pods (not another container within an existing pod)
BUT: we can have more containers in the same pod (but not with the same stuff in it)

### Multi-Container Pods

### create a pod
kubectl run

Documentation: https://kubernetes.io/docs/concepts/workloads/pods/


# YAML Files

Yaml file is used to represent data. In this case (kubernetes) configuration data.

Key - Value

Fruit: Apple
Vegetable: Potato

Array:

Fruits: 
 - Orange
 - Apple
 - Banana
