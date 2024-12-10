For the article of this repo, please refer to: https://www.swtestacademy.com/deploy-full-stack-application-in-kubernetes/

## INSTRUCTIONS

## Update System Packages If need: ensure your system packages are up-to-date:

``` sudo apt update && sudo apt upgrade -y ```

## Install Required Dependencies
## Install necessary dependencies like curl, conntrack, and a container runtime:

``` sudo apt install -y curl apt-transport-https conntrack ``` 

## If Docker is not already installed, follow these commands to install it:

``` sudo apt install -y docker.io ``` 
``` sudo systemctl enable docker ``` 
``` sudo systemctl start docker ``` 
``` sudo usermod -aG docker $USER ``` 

## Install Minikube

``` curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64 ```
``` sudo install minikube-linux-arm64 /usr/local/bin/minikube ```

## Start Minikube
``` minikube start ```

## Verify the Cluster

``` minikube status ```

## Build your Docker images inside the Minikube environment:
``` eval $(minikube docker-env) ``` 

## Verify that your Docker environment is now pointing to Minikube:
``` docker info ``` 

## Build Your Docker Image

``` docker build -t backend:latest . ``` 
``` docker build -t frontend:latest . ``` 

## Verify the Image is Available in Minikube

``` docker images ```

## Apply the Configures: deploy the application components using kubectl.

``` kubectl apply -f backend.yaml ```
``` kubectl apply -f frontend.yaml ```
``` kubectl apply -f database.yaml ```

## Verify the Deployment by checking the status of the pods and services:

``` kubectl get pods ``` 
``` kubectl get services ``` 

## Find the Node’s IP

``` Minikube ip ``` 

## Access UI via the Node’s IP

``` http://192.168.49.2:30000/ ``` 


