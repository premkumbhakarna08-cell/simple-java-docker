pipeline {
    agent any

    environment {
        IMAGE_NAME = "premk26/simple-java-docker"
        TAG = "build-${1.0}"
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
                javac -d out $(find src "Main.java")
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t premk26/simmple-java-docker .
                docker tag premk26/simple-java-docker:1.0 premk26/simple-java-docker:latest
                '''
            }
        }

