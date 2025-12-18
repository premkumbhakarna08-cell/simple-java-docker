pipeline {
    agent any

    environment {
        IMAGE_NAME = "premk26/simple-java-docker"
        TAG = "1.0"
    }

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Compile Java') {
            steps {
                sh '''
                mkdir -p out
                javac -d out $(find src -name "*.java")
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh """
                docker build -t ${IMAGE_NAME}:${TAG} .
                docker tag ${IMAGE_NAME}:${TAG} ${IMAGE_NAME}:latest
                """
            }
        }
     } // closes stages 
 } // closes pipeline
