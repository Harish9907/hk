pipeline {
    agent any

    environment {
        IMAGE_NAME = 'harish0799/hk-flask-app'
    }

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f flask-app/k8s/deployment.yaml'
                sh 'kubectl apply -f flask-app/k8s/service.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'kubectl get pods'
                sh 'kubectl get svc'
            }
        }
    }
}
