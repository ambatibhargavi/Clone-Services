pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/ambatibhargavi/Clone-Services.git'
        IMAGE_NAME = 'bharu2003/netflix-clone:v1'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "${REPO_URL}", branch: 'main' // Specify the branch here if it's not 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image directly
                    docker.build("${IMAGE_NAME}:${env.BUILD_NUMBER}")
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    // Ensure kubectl is configured to communicate with your Kubernetes cluster
                    sh '''
                    kubectl apply -f deployment.yaml
                    kubectl apply -f service.yaml
                    '''
                }
            }
        }
    }

    post {
        always {
            // Archive artifacts if needed
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}
