pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-django-app .'
            }
        }
        
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8000:8000 my-django-app'
            }
        }
    }
    
    post {
        always {
             echo 'Performing cleanup...'
        }
        
        success {
            echo 'Pipeline succeeded!'
        }
        
        failure {
            echo 'Pipeline failed!'
        }
    }
}
