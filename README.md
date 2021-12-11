# devops-test
imaserver!

# Detailed Step on how I was able to carry out the test

## Deployment Requirement

* EKS CLuster
* Docker image built from the Dockerfile
* Deployment Script
* Testing 

## Deployment Script
In setting up the Kubernetes deployment, I had write a yaml file that would automate deployment, stating the number of replicas to be 3 incase of failovers, also while there is a downtime, the max unavailable node to be 1, so even the minimun number of nodes that can be down is 2 after which if there is any other node failure, it will automatically be replaced by the replicaset, this which will also take place in the space of 5 seconds as state by the minReady seconds.

The container port exposed for communication with the docker image is port 3000, also the CPU and Memory limits were set a considerable value.

## Dockerfile

The Dockerfile contain a set of instructions to be performed by docker by pulling the node:16-alpine3.11 image from the public registry which will then be built against the dependencies in the package.json file, after which it will be built using 
```npm run build``` command.

