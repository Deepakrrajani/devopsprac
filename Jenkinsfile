pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Checkout source code from SCM (e.g., Git)
                checkout scm
                
                // Build Docker image
                script {
                    def dockerImage = docker.build('Deepak:latest', '.')
                }
            }
        }
        
        stage('Push') {
            steps {
                // Push Docker image to a Docker registry (optional)
                script {
                    docker.withRegistry('https://registry.example.com', 'docker-credentials-id') {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
