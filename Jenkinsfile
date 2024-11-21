pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    // Example of running shell commands
                    sh 'echo Installing dependencies...'
                    sh 'pip install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Example of running test commands
                    sh 'pytest'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Example of deploy commands
                    sh 'deploy.sh'
                }
            }
        }
    }
}


