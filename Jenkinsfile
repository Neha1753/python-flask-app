pipeline {
    agent any
stage('Setup Python Environment') {
            steps {
                script {
                    sh 'python3 -m venv venv'
                    sh 'source venv/bin/activate'
                    sh 'pip install -r requirements.txt'
                }
            }
        }
    stages {
        stage('Checkout') {
            steps {
                sh 'python3 --version'
sh 'pip3 --version'
            }
        }
        stage('Build') {
            steps {
                script {
                    // Example of running shell commands
                    sh 'echo Installing dependencies...'
                    sh 'pip3 install -r requirements.txt'
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


