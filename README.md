# DeployingDotNetMicroservices
Deploying .Net Microservices to Azure Kubernetes Service

This repo shows three .NET microservices forming an example application.
1) Shopping.API is a very simple WEB API project.
2) Shopping Client is a very simple MVC project.
3) Mongo DB.

Shopping Client consumes API project which in turn retrieves data from MongoDB.
The aim of this repo is to show how to build and containerize .NET microservices.

Both projects (API, Client) are built and containerized from scratch using Docker and can be composed with Docker Compose.

Prerequisits:
- install and setup any kind of docker system (eg. docker-desktop for windows)
- install and setup Kubernetes (eg. Minikube on Linux or enable Kubernetes on docker-desktop)

1) Most simple scenario (when you have no Kubernetes installed)
- to run the projects on your local docker environment, issue the following command:
docker-compose -f docker-compose.yml up -d

- to stop the projects:
docker-compose -f docker-compose.yml down

2) If you have local Kubernetes setup, apply the yaml files in dir 'k8s'

3) You can also run the complete solution on Azure Cloud using Azure Kubernetes Service and Azure Container Registry.
This step requires you to create a Free Trial account on Azure. 
You can find azure commands in 'aks' folder.

Unfortunately it is not enabled to run Azure Pipelines to create and automate CI/CD with Free Trial account. (Therefore I didn't upload pipeline yaml files into the repo.)



