pipeline {
    agent any

    environment {
        IMAGE_NAME = 'harish0799/hk-flask-app'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/harish9907/hk.git'
            }
        }
      
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}

