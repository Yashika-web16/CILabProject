# CILabProject
CI and Jenkins Assignment


## Project Description
This project demonstrates Jenkins CI/CD using Freestyle and Multibranch Pipeline jobs.  
It includes automated builds, tests, and notifications using GitHub integration.

---

## Folder Structure
CILabProject/

├── src/
│ ├── main/
│ │ ├── java/com/muj/ci/Calculator.java
│ │ └── resources/
│ └── test/
│ └── java/com/muj/ci/CalculatorTest.java
│
├── pom.xml # for Maven
│ OR
├── build.gradle # for Gradle
│
├── Jenkinsfile
│
├── docker/
│ └── Dockerfile
│
├── scripts/
│ ├── build.sh / build.bat
│ └── deploy.sh
│
└── README.md


---

## How to Run
1. Install Jenkins on local machine  
2. Configure Global Tools (JDK, Git, Maven)  
3. Install required plugins (Pipeline, Git, Email Extension, etc.)  
4. Create Freestyle and Multibranch Pipeline jobs  
5. Push code to GitHub → Jenkins builds automatically via webhook  

---

## Installation Guide

### 1. Jenkins Installation
- Download Jenkins LTS: https://www.jenkins.io/download/
- Install Java JDK 11 or later
- Install Git for Windows
- Run Jenkins and complete initial setup
- Install recommended plugins

---

### 2. Configure Jenkins
- Configure Global Tool Configuration:
  - JDK
  - Git
  - Maven
- Configure Jenkins URL
- Set up SMTP for email notifications

---

### 3. Security
- Configure security realm: Jenkins own user database
- Set up authorization: Matrix-based security
- Enable CSRF protection

---

### 4. Verify Installation
- Open Jenkins Dashboard
- Ensure all plugins are installed
- Ensure jobs can build successfully

---

## User Manual

### Freestyle Job
1. Go to Jenkins Dashboard
2. Open Freestyle Job
3. Click **Build Now**
4. Check console output for results
5. Push changes to GitHub → Webhook triggers automatic build

---

### Multibranch Pipeline
1. Go to Jenkins Dashboard
2. Open Multibranch Pipeline
3. Click **Scan Multibranch Pipeline Now**
4. Jenkins detects branches and runs builds according to Jenkinsfile
5. View console output for each branch build

---

## Troubleshooting Guide

### 1. Jenkinsfile Not Found
- Ensure Jenkinsfile is in the root of the repository
- Scan Multibranch Pipeline again

---

### 2. Build Fails Due to Missing Plugins
- Go to Manage Jenkins → Manage Plugins
- Install required plugins
- Restart Jenkins if necessary

---

### 3. Webhook Not Triggering Build
- Verify GitHub webhook URL:
http://localhost:8080/user/yashika_04/
- Ensure ngrok is running if accessing locally from GitHub
- Check webhook delivery logs on GitHub

---

### 4. Pipeline Skipping Branches
- Ensure branch names match patterns in Jenkinsfile
- Check Multibranch Pipeline indexing

