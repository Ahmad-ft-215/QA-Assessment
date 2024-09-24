# QA-Assessment

#Prerequisites
Before starting, ensure you have the following installed:
1. Docker
2. Minikube
3. Kubectl
4. PowerShell (for running commands)

# Step 1: Backend Deployment

1. Use Minikube’s Docker daemon to build the image.
   commands:
     1. minikube docker-env | Invoke-Expression
     2. docker build -t backend-service
2. Apply Backend Deployment using below command
     command:
       1. kubectl apply -f deployment.yaml
3. We can also Veirfy Backend Service with below methods
       1.command to check the backend service is running
           kubectl get services
       2. Or We can also test it by port forwaring
         command to forward port: kubectl port-forward service/backend-service 3000:3000 
         Then, open http://localhost:3000/greet in a browser.

# Step 2: Frontend Deployment

1. Build the Frontend Docker Image
   command :
     docker build -t frontend-service
2. Apply Frontend Deployment using below command
   command:
     kubectl apply -f frontend-deployment.yaml
3. Access the Frontend using below command
   command:
     minikube service frontend-service


