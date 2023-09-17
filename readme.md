# Notes about kubernetes

# Major commands

kubectl run hello-mini-kube <br/>
kubectl cluster-info</br>
kubectl get nodes<br/>
 
to see the pods: kubectl get pods

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

kubectl create -f mypod.yaml
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

Dictionary/Map:

Banana:
  Calories: 105
  Fat: 0.4g

Grapes: 
  Calories: 20
  Fat: XX

### Creating a pod using a yamle based configuration file

Kubernetes uses yaml files as inputs for the creation of objects such as pods, deployments. All of this follow similar structure:
4 properties/fields:

apiVersion: v1
kind: Pod 
metadata: # data about the object, in form of dictionary
   name: myapp-pod
   labels:
     app: myapp
     type: front-end
spec:
   containers:
      - name: nginx-container
        image: nginx
     

## Create a Pod 

To start a pod in Kubernetes, you typically create a YAML file that defines the pod configuration and then use the kubectl command-line tool to create the pod.

Here is an example of a simple YAML file for a pod:

apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
  - name: mycontainer
    image: nginx

In this example, a pod named mypod is created with a single container named mycontainer that runs the nginx image.

To create the pod, save the YAML content to a file, for example, mypod.yaml, and then use the kubectl create command:

kubectl create -f mypod.yaml

The kubectl create -f command will create the pod defined in the specified file.

Make sure you have a running Kubernetes cluster and you have configured kubectl to connect to it before running the command.