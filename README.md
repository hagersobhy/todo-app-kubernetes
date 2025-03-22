# 🚀 Deploying Todo App on Kubernetes

## 📌 Project Overview  
This project sets up a **Todo App** on Kubernetes using **MySQL** as the database. The setup leverages **StatefulSets**, **Secrets**, and **LoadBalancer Services** to ensure scalability, persistence, and secure management of database credentials.

---

## 🎯 Purpose  
- **Scalability**: Easily scale the application using Kubernetes StatefulSets.  
- **Persistence**: Ensure data persistence with Persistent Volume Claims (PVCs).  
- **Security**: Securely manage database credentials using Kubernetes Secrets.  
- **Accessibility**: Provide external access to the application using LoadBalancer Services.  

---

## 🔧 Technologies Used  
- **Kubernetes**: Container orchestration platform.  
- **MySQL**: Relational database management system.  
- **StatefulSets**: Kubernetes resource for managing stateful applications.  
- **Secrets**: Kubernetes resource for managing sensitive information.  
- **LoadBalancer**: Kubernetes service type for external access.  

---

## 🏗️ Architecture  
The Todo App Kubernetes setup consists of the following components:  
1. **MySQL Database**: Deployed as a StatefulSet for data persistence.  
2. **Secret Management**: Securely stores database credentials.  
3. **Persistent Storage**: Uses Persistent Volume Claims (PVCs) for data storage.  
4. **LoadBalancer Service**: Provides external access to the Todo App.  

---
## 📂 Project Structure  
The project is structured as follows:  
```
todo-app-kubernetes/
├── k8s/
│ ├── mysql-secret.yaml
│ ├── mysql-statefulset.yaml
│ ├── mysql-service.yaml
│ ├── todo-app-statefulset.yaml
│ ├── todo-app-service.yaml
├── README.md
```
---

## 📌 Setup Instructions  

### 1️⃣ Prerequisites  
Ensure you have:  
- **A running Kubernetes cluster**: (Minikube, GKE, EKS, AKS, etc.)  
- **kubectl**: Installed and configured.  
- **Docker**: (Optional for building custom images).  

---

### 2️⃣ Clone the Repository  
Clone the repository to your local machine:  
```  
docker pull hagersobhy728/getting-started:latest
```
---
### 3️⃣ Deploy the Application  
Apply the Kubernetes manifests to deploy the application:  
```
kubectl apply -f k8s/  
```
---
### 4️⃣ Verify Deployment  
Check the status of the deployed pods and services:  
``` 
kubectl get pods  
kubectl get svc
```
----
### 5️⃣ Access the Application  
- **Minikube**:  
  ``` 
  minikube service todo-app
  ```
  ---
  ### 6️⃣ Database Access  
To connect to the MySQL database:  
```  
kubectl port-forward pod/mysql-0 3306:3306  
mysql -h 127.0.0.1 -u root -p
```
---
## 🧹 Cleanup  
To remove all deployed resources:  
``` 
kubectl delete -f k8s/
```
---
## 🚀 Future Enhancements  
- **Horizontal Pod Autoscaling (HPA)**: Implement autoscaling based on CPU/memory usage.  
- **CI/CD Pipeline**: Integrate a CI/CD pipeline for automated deployments.  
