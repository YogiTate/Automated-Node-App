pipeline {
    agent any

    environment {
        DOCKER_USERNAME = "yogi93676"
        IMAGE_NAME = "automated-node-app"
        IMAGE = "${DOCKER_USERNAME}/${IMAGE_NAME}"
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
                sh '''
                docker build -t $IMAGE:$TAG .
                '''
            }
        }

        stage('Push Docker Image') {
            steps {
                sh '''
                docker push $IMAGE:$TAG
                '''
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop automated-node-app || true
                docker rm automated-node-app || true

                docker run -d \
                -p 3000:3000 \
                --name automated-node-app \
                $IMAGE:$TAG
                '''
            }
        }

        stage('Show Image URL') {
            steps {
                sh '''
                echo "Docker Hub URL:"
                echo "https://hub.docker.com/r/$IMAGE"
                '''
            }
        }

    }
}


