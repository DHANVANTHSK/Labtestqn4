pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Show Build Info') {
            steps {
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB_NAME: ${env.JOB_NAME}"
                echo "WORKSPACE: ${env.WORKSPACE}"
            }
        }
        
        stage('Run Linter') {
            steps {
                // Use bat instead of sh for Windows environments
                bat 'pip install flake8'
                bat 'flake8 app.py'
            }
        }
    }
}
