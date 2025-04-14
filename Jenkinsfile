pipeline {
    agent any
   
    environment {
        DOCKER_CREDENTIALS = credentials('Docker_Cred')
        IMAGE_NAME = 'yogeshsaidani/node-todo'
        DOCKER_TAG = 'latest'
    }
   
    stages {
        stage('Clone Code') {
            steps {
                checkout scm
            }
        }
       
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                sh """
                docker build -t ${IMAGE_NAME}:${DOCKER_TAG} .
                """
            }
        }
       
        // stage('Login to Docker Hub') {
        //     steps {
        //         // Login to Docker Hub using Jenkins credentials
        //         sh """
        //         echo ${DOCKER_CREDENTIALS_PSW} | docker login -u ${DOCKER_CREDENTIALS_USR} --password-stdin
        //         """
        //     }
        // }
 
        // stage('Push Docker Image') {
        //     steps {
        //         script {
        //             // Push the Docker image to Docker Hub
        //             sh """
        //             docker push ${IMAGE_NAME}:${DOCKER_TAG}
        //             """
        //         }
        //     }
        // }
       
        // stage('Run Docker Container Locally') {
        //     steps {
        //         script {
        //             // Run the Docker container locally
        //             sh """
        //             docker run -d -p 8080:8080 ${IMAGE_NAME}:${DOCKER_TAG}
        //             """
        //         }
        //     }
        // }
    }
}