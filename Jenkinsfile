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
                bat '''
                if not exist out mkdir out
                javac -d out src\\Main.java
                '''
            }
        }

    
                 stage('Build Docker Image') {
            steps {
                bat """
                docker build -t %IMAGE_NAME%:%TAG% .
                docker tag %IMAGE_NAME%:%TAG% %IMAGE_NAME%:latest
                """
            }
        }
     } // closes stages 
 } // closes pipeline
