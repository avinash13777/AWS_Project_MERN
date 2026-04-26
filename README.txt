**Project Title:** Deployment of MERN Stack Application on AWS with Load Balancer, Nginx, PM2, MongoDB Atlas, and Cloudflare

**GitHub Repository:**
https://github.com/avinash13777/AWS_Project_MERN
URL Need to access :

http://www.avinashcloud.online/

---

## 1. Project Overview

This project demonstrates deployment of a MERN (MongoDB, Express, React, Node.js) application on AWS infrastructure. The backend API is deployed on EC2 instances and managed using PM2, while Nginx is used as a reverse proxy. High availability is achieved using an AWS Application Load Balancer, and DNS with SSL is configured using Cloudflare.

---

## 2. Architecture Components

* AWS EC2 (multiple instances)
* Application Load Balancer (ALB)
* Nginx (reverse proxy)
* Node.js + Express backend
* MongoDB Atlas (cloud database)
* PM2 (process manager)
* Cloudflare (DNS + SSL)
* Domain: avinashcloud.online

---

## 3. Step-by-Step Implementation

### Step 1: Backend Setup

* Created Node.js Express application
* Connected to MongoDB Atlas using Mongoose
* Created APIs (`/hello`, `/trip`)
* Used environment variables (`.env`)

---

### Step 2: EC2 Setup

* Launched Ubuntu EC2 instance
* Installed:

  * Node.js
  * Git
  * Nginx
  * PM2
* Cloned project from GitHub
* Started backend using:

  ```
  pm2 start index.js --name travel-backend
  ```

---

### Step 3: Nginx Configuration

* Configured reverse proxy:

  * Port 80 → Node app (3000)
* Restarted Nginx
* Verified using:

  ```
  http://<EC2-IP>/api/hello
  ```

---

### Step 4: Load Balancer Setup

* Created Application Load Balancer
* Added multiple EC2 instances
* Configured target group (port 3000)
* Verified traffic distribution

---

### Step 5: AMI & Scaling

* Created AMI from configured instance
* Launched multiple instances from AMI
* Ensured backend auto-start (PM2)

---

### Step 6: Domain & Cloudflare Setup

* Purchased domain: avinashcloud.online
* Added domain to Cloudflare
* Updated nameservers
* Configured DNS:

  * A record → Load Balancer DNS
* Enabled SSL (Flexible)

---

### Step 7: Frontend Deployment (Optional)

* Built React app (`npm run build`)
* Deployed static files to `/var/www/html`
* Served via Nginx

---

## 4. Key Features

* High availability using Load Balancer
* Process management using PM2
* Reverse proxy using Nginx
* Secure DNS with Cloudflare SSL
* Scalable architecture using AMI

---

## 5. Outcome

Successfully deployed a scalable MERN backend accessible via:

* Domain URL
* Load Balancer DNS

---

## 6. Learnings

* AWS EC2 & networking
* Load balancing concepts
* Nginx reverse proxy
* CI/CD basics with GitHub
* Cloudflare DNS & SSL setup
* Debugging real-world deployment issues

---

## 7. Future Enhancements

* Full frontend integration
* CI/CD pipeline (GitHub Actions)
* HTTPS using AWS ACM
* Auto Scaling Group

---

