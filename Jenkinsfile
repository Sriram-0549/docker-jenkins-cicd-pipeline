pipeline {
    agent any

    environment {
        IMAGE_NAME = "sriramcj/docker-jenkins-cicd"
        IMAGE_TAG = "latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Sriram-0549/docker-jenkins-cicd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'Dockerhub',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f node-app || true
                docker run -d --name node-app -p 3001:3000 $IMAGE_NAME:$IMAGE_TAG
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline Completed Successfully!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}
