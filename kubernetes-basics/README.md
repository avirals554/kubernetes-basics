# Kubernetes Basics Implementation

This repository contains a basic implementation of Kubernetes concepts and configurations. It serves as a learning resource and a starting point for working with Kubernetes.

## Status

⚠️ **Work in Progress**  
This project is currently under development. More features and examples will be added over time.

## Contents

- BAsic Kubernetes manifests (Pods, Deployments, Services, etc.)
- Example configurations
- Simple application deployments

## Getting Started

1. Ensure you have `kubectl` installed and configured
2. Clone this repository
3. Apply the manifests using `kubectl apply -f <filename>`

Contributions and suggestions are welcome!

## replication-controller (for creating more than one pod)
1. i have created a file named replication-controller.yaml 
2. the replica key has 3 as a value meaning it will create 3 different pods of the same app/stuff in my example im using nginx.
3. for simplicity im just using one container in the pods after that i will update it to have more than one.
4. the template are the metadata and specs of the pods you want to run .
5. to create the replication controller or rather run it and the status check are  -
    ~kubectl create replicationcontroller.yaml
    ~ kubectl get replicationcontroller
    ~kubectl get pods
// ignore any spelling mistakes, idont like this keyboard
## replication-set(somehow this is supposed to be better than the controller)
1. replica-set has one difference it has a selector field after the template one.
2. apparently it can also control pods that are not specified in its own definition.
3. a replica-set automatically ensures that there are exactly as many pods as specified in the definition in the yaml file.
4. a replica-set automatically ensures that there are exactly as many pods as specified in the definition in the yaml file.

## deployment
1. deployment is the next step for automation of softwares after replication sets 
2. deployment is used for updates or shall we say changes that maybe made to the softwares/programmes withing the pods that are made by a replicaset .
3. deployment manages the replica-set , so we dont really have to mind/ manage them at all, we will see how well it scales.
4. here is some copied info from deepseek if my language is too casual for you:-
A Deployment is a higher-level abstraction that manages ReplicaSets and provides declarative updates to applications. It allows you to:
    Roll out new versions of your app (with rolling updates, blue-green, or canary deployments)
    Roll back to a previous version if something goes wrong.
    Scale the number of replicas.
    Pause and resume updates.
# things to remember:-
1. Kind: Deployment
2. matchLabels:
      name: ---- the name here should be same as 
template:
     metadata: 
                labels: 
                 name: --- the name here

#kubernetes#
##deployment##
### ~kubectl rollout status deployment/myapp-deployment. ###  //this is just a name dont take this seriously.
### ~kubectl rollout history deployment/myapp-deployment.
##updates##
1. whenever doing an update the deployment and make some changes to it , the deployment will fist stop a pod and then create another pod with the updates settings this is done one by one as to maintain the accesibility of the app rather than completly stop then application all together to update the changes.

## commands to remember##
1. kubectl create -f deployment-definition.yml
2. kubectl get deployments
3. kubectl apply -f dep
