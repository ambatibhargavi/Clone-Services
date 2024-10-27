pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ambatibhargavi/Clone-Services.git', branch: 'main'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                // Apply Kubernetes configuration files
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
