🚀 Employee Management System – CI/CD with Jenkins

A real-time Java Spring Boot application integrated with a Jenkins CI/CD Pipeline.
This project demonstrates how companies automate build, test, and package stages using Jenkins.

📌 Project Overview

This application provides a simple REST API to fetch employee details.
It is mainly used to practice Jenkins pipelines for Java-based microservices.

🔹 Real-World Use Case

Used in enterprise environments for:

HR systems

Internal employee portals

DevOps CI/CD pipeline demonstrations

🛠️ Tech Stack
Technology	Purpose
Java 17	Application development
Spring Boot	REST API
Maven	Build & dependency management
Jenkins	CI/CD Pipeline
GitHub	Source code management
📂 Project Structure
employee-management/
│
├── Jenkinsfile
├── pom.xml
├── README.md
└── src
    └── main
        └── java
            └── com/example/employee
                ├── EmployeeApplication.java
                ├── controller
                │   └── EmployeeController.java
                └── model
                    └── Employee.java

🔄 Jenkins CI/CD Pipeline Flow

Checkout Code from GitHub

Build the project using Maven

Run Tests

Package the application into JAR

Archive Artifacts

🧩 Jenkinsfile Pipeline
pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'Java17'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/your-username/employee-management.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }

    post {
        success {
            echo 'Build Successful ✅'
        }
        failure {
            echo 'Build Failed ❌'
        }
    }
}

🖼️ Screenshots (Photos)
📸 Jenkins Pipeline Job

📸 Jenkins Build Stages

📸 Jenkins Console Output

📸 Build Artifact (JAR)

📸 REST API Output

📁 Screenshot Folder Structure
screenshots/
├── jenkins-job.png
├── jenkins-pipeline-stages.png
├── jenkins-console-output.png
├── jenkins-artifact.png
└── api-output.png


👉 Tip:
Take screenshots from Jenkins UI and save them in a folder named screenshots.

▶️ How to Run Locally
1️⃣ Clone Repository
git clone https://github.com/your-username/employee-management.git
cd employee-management

2️⃣ Build Application
mvn clean package

3️⃣ Run Application
java -jar target/employee-management-1.0.jar

4️⃣ Access API
http://localhost:8080/employee

📤 Jenkins Setup Instructions

Install Java 17 and Maven

Configure tools in:

Manage Jenkins → Global Tool Configuration

Create Pipeline Job

Choose Pipeline script from SCM

Add GitHub repository URL

Click Build Now

✅ Expected Output
{
  "id": 101,
  "name": "Noe",
  "role": "DevOps Engineer"
}

