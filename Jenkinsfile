pipeline {
    agent any

    tools {
        maven 'maven3'
        jdk 'jdk'
    }

    stages {

        stage('Verify Tools') {
            steps {
                sh '''
                java -version
                mvn -version
                '''
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kalladavid/-Employee-Management-System-CI-CD-with-Jenkins.git'
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
    }
}
