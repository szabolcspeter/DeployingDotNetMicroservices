# DeployingDotNetMicroservices
Deploying .Net Microservices to Azure Kubernetes Service

This repo shows three .NET microservices forming an example application.
1) Shopping.API is a very simple WEB API project.
2) Shopping Client is a very simple MVC project.
3) Mongo DB.

Shopping Client consumes API project which in turn retrieves data from MongoDB.
The aim of this repo is to show how to build and containerize .NET microservices.

Both projects (API, Client) are built and containerized from scratch using Docker and can be composed with Docker Compose.
In addition to this, you can apply example yaml files placed in folder "k8s" to deploy them on your local Kubernetes cluster.
Finally, files from folder "aks" can be used to deploy the application in Azure AKS using Azure ACS.

You have 3 different ways to run the application: 

## 1) using docker compose (when you have no Kubernetes installed)
   *Prerequisits:\
      &nbsp;&nbsp;&nbsp;- install and setup any kind of docker system (eg. docker-desktop for windows)*\
   \
   start:\
      &nbsp;&nbsp;&nbsp;- **docker-compose -f docker-compose.yml up -d**\
   stop:\
      &nbsp;&nbsp;&nbsp;- **docker-compose -f docker-compose.yml down**
## 2) If you have local Kubernetes setup, apply the yaml files in dir 'k8s'
   *Prerequisits:\
      &nbsp;&nbsp;&nbsp;- docker images must be created from Web API and MVC projects. See dockerfiles from step 1\
      &nbsp;&nbsp;&nbsp;- install and setup Kubernetes (eg. Minikube on Linux or enable Kubernetes on docker-desktop)*\
   \
   start:\
      &nbsp;&nbsp;&nbsp;- **kubectl apply -f <"k8s" folder>**\
   stop:\
      &nbsp;&nbsp;&nbsp;- **kubectl delete -f <"k8s" folder>** 
 
## 3) You can also run the complete solution on Azure Cloud using Azure Kubernetes Service and Azure Container Registry.
   *Prerequisits:\
      &nbsp;&nbsp;&nbsp;- This step requires you to create a Free Trial account on Azure.\
      &nbsp;&nbsp;&nbsp;- In order to setup, docker images must be created from Web API and MVC projects.See dockerfiles from step 1\
      &nbsp;&nbsp;&nbsp;- On Azure portal you need to setup Kubernetes AKS and ACS.\
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;You can use Azure CLI as well. You can use commands.txt in "aks" folder.*\
    start:\
      &nbsp;&nbsp;&nbsp;- **kubectl apply -f <"aks" folder>**\
    stop:\
      &nbsp;&nbsp;&nbsp;- **kubectl delete -f <"aks" folder>**
      
## Azure DevOPS
**Unfortunately you can't run Azure Pipelines to create and automate CI/CD using Free Trial account. Therefore I didn't push pipeline yaml files to repo.**



