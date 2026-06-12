# 🚀 AWS Docker Kubernetes SNS Project

## 📌 Project Overview

This project demonstrates the complete deployment of a Node.js application on AWS using Docker and Kubernetes (K3s). The application is containerized with Docker, deployed on Kubernetes, and integrated with Amazon SNS for email notifications.

---

# 🏗️ Architecture

👤 User
   │
   ▼
☁️ AWS EC2 Instance
   │
   ▼
🐳 Docker Container
   │
   ▼
☸️ Kubernetes (K3s)
   │
   ▼
📦 Deployment
   │
   ▼
🌐 NodePort Service
   │
   ▼
🟢 Node.js Application
   │
   ▼
📧 Amazon SNS Notification
```

# 🛠️ Technologies Used

* ☁️ AWS EC2
* 📧 AWS SNS
* 🔐 AWS IAM Role
* 🐳 Docker
* ☸️ Kubernetes (K3s)
* 🟢 Node.js
* 🐧 Amazon Linux 2023
* 🔧 AWS CLI
* 🌿 Git
* 🐙 GitHub

---

# 📂 Project Structure

```text
aws-docker-kubernetes-project/
│
├── app.js
├── package.json
├── dockerfile
├── deployment.yaml
├── service.yaml
├── README.md
└── screenshots/
```

---

# ⚙️ Project Workflow

## 1️⃣ Launch EC2 Instance

* Create AWS EC2 instance
* Configure Security Group
* Attach IAM Role with SNS permissions

---

## 2️⃣ Connect to EC2

```bash
ssh -i "key.pem" ec2-user@<PUBLIC-IP>
```

---

## 3️⃣ Clone Repository

```bash
git clone https://github.com/Puneet-Xt/aws-docker-kubernetes-project.git

cd aws-docker-kubernetes-project
```

---

## 4️⃣ Build Docker Image

```bash
docker build -t devops-app:v1 .
```

✅ Creates Docker image for the Node.js application.

---

## 5️⃣ Run Docker Container

```bash
docker run -d -p 3000:3000 --name devops-container devops-app:v1
```

Verify:

```bash
docker ps
```

---

## 6️⃣ Test Application

```bash
curl localhost:3000
```

Or open:

```text
http://<PUBLIC-IP>:3000
```

---

## 7️⃣ Deploy to Kubernetes

```bash
kubectl apply -f deployment.yaml

kubectl apply -f service.yaml
```

---

## 8️⃣ Verify Kubernetes Resources

### Check Pods

```bash
kubectl get pods
```

### Check Deployments

```bash
kubectl get deployments
```

### Check Services

```bash
kubectl get svc
```

---

## 9️⃣ Access Application

Open in browser:

```text
http://<PUBLIC-IP>:30080
```

---

## 🔟 Send SNS Notification

```bash
aws sns publish \
--topic-arn <SNS-TOPIC-ARN> \
--message "Deployment Successful" \
--subject "DevOps Project"
```

📩 Email notification will be delivered to subscribed users.

---

# 📸 Project Screenshots

## ☁️ EC2 Instance Running

Add screenshot:

```text
screenshots/ec2-instance.png
```

---

## 🐳 Docker Container Running

Add screenshot:

```text
screenshots/docker-ps.png
```

---

## ☸️ Kubernetes Pods

Add screenshot:

```text
screenshots/kubectl-pods.png
```

---

## 🌐 Kubernetes Service

Add screenshot:

```text
screenshots/kubectl-service.png
```

---

## 🖥️ Application Running in Browser

Add screenshot:

```text
screenshots/browser-output.png
```

---

## 📧 SNS Email Notification

Add screenshot:

```text
screenshots/sns-email.png
```

---

# 🎯 Skills Demonstrated

✅ AWS EC2 Management

✅ IAM Role Configuration

✅ Docker Containerization

✅ Kubernetes Deployment

✅ Kubernetes Service Management

✅ AWS SNS Integration

✅ Linux Administration

✅ Git & GitHub

✅ Troubleshooting and Debugging

✅ Cloud Infrastructure Management

---

# 🚨 Challenges Faced & Solutions

## ❌ Kubernetes Node NotReady

### Problem

Low memory caused Kubernetes node instability.

### Solution

✅ Added 2 GB Swap Memory

✅ Restarted K3s Service

---

## ❌ DiskPressure Error

### Problem

Node entered DiskPressure state due to insufficient storage.

### Solution

✅ Increased EBS Volume

```text
8 GB ➜ 20 GB
```

✅ Expanded Filesystem

✅ Restarted K3s

---

## ❌ ErrImageNeverPull

### Problem

Kubernetes could not locate the Docker image.

### Solution

✅ Export Docker image

```bash
docker save devops-app:v1 -o devops-app.tar
```

✅ Import into K3s

```bash
sudo k3s ctr images import devops-app.tar
```

---

# 🚀 Future Improvements

* 🔄 Jenkins CI/CD Pipeline
* 🏗️ Terraform Infrastructure as Code
* 📊 Prometheus Monitoring
* 📈 Grafana Dashboards
* 🌐 Kubernetes Ingress
* 🔒 SSL/HTTPS Integration
* ⚡ Automated Deployments

---

# 🎉 Project Outcome

Successfully deployed a Node.js application on AWS using Docker and Kubernetes, exposed it through a NodePort Service, integrated SNS notifications, and managed the complete deployment lifecycle on an EC2 instance.

---

# 👨‍💻 Author

**Puneet Choudhary**

🐙 GitHub: https://github.com/Puneet-Xt
