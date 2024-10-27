pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/ambatibhargavi/Clone-Services.git'
        IMAGE_NAME = 'bharu2003/netflix-clone:v1'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the Git repository
                git url: "${REPO_URL}", branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Set up Docker to use Minikube's Docker daemon (if using Minikube)
                    sh 'eval $(minikube docker-env)'

                    // Build the Docker image
                    docker.build("${IMAGE_NAME}:${env.BUILD_NUMBER}")
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    // Deploy to Kubernetes using kubectl commands
                    sh '''
                    kubectl apply -f k8s/deployment.yaml
                    kubectl apply -f k8s/service.yaml
                    '''
                }
            }
        }
    }

    post {
        always {
            // Archive any artifacts produced by the pipeline if needed
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}
