pipeline {
    agent any

    environment {
        IMAGE_NAME = "yogi93676/automated-node-app"
        TAG = "latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/YogiTate/Automated-Node-App.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$TAG .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push $IMAGE_NAME:$TAG'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop automated-node-app || true
                docker rm automated-node-app || true
                docker run -d -p 3000:3000 --name automated-node-app $IMAGE_NAME:$TAG
                '''
            }
        }
    }
}

