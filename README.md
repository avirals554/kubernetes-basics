# Kubernetes Basics Implementation

This repository contains a basic implementation of Kubernetes concepts and configurations. It serves as a learning resource and a starting point for working with Kubernetes.

## Status

⚠️ **Work in Progress**  
This project is currently under development. More features and examples will be added over time.

## Contents

- Basic Kubernetes manifests (Pods, Deployments, Services, etc.)
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
3. a replica-set automatically ensures that there are exactly as many pods as specified in the definition in the yaml file.
4.
