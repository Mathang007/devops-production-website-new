pipeline {
    agent any
    environment {
        IMAGE_NAME = "devops-production-website"
        IMAGE_TAG  = "${BUILD_NUMBER}"
    }
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                  docker build -t $IMAGE_NAME:$IMAGE_TAG .
                '''
            }
        }

        stage('List Docker Images') {
            steps {
                sh 'docker images | grep $IMAGE_NAME'
            }
        }
    }
}

