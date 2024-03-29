pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                sh 'docker build -t my-django-app .'
            }
        }
        
        stage('Run Docker Container') {
            steps {
                // Run Docker container
                sh 'docker run -d -p 8000:8000 my-django-app'
            }
        }
    }
    
    post {
        always {
            // Clean up steps, if any
        }
        
        success {
            // Actions to take if the pipeline succeeds
            echo 'Pipeline succeeded!'
        }
        
        failure {
            // Actions to take if the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}
