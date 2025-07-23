pipeline {
    agent any

    environment {
        IMAGE_NAME = 'harish0799/hk-flask-app'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/harish9907/hk.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                dir('k8s') {
                    sh '''
                        kubectl apply -f deployment.yaml
                        kubectl apply -f service.yaml
                    '''
                }
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

