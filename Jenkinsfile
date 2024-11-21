pipeline {
    agent any

    environment {
        // Define the virtual environment directory
        VENV_DIR = 'venv'
    }

    stages {
        stage('Checkout SCM') {
            steps {
                // Checkout code from the repository
                checkout scm
            }
        }

        stage('Setup Python Environment') {
            steps {
        script {
            try {
                sh 'python3 --version'
            } catch (Exception e) {
                echo 'Python not found, installing Python and pip...'
                sh 'apt-get update && apt-get install python3 python3-pip -y'
            }
        }
    }
        }

        stage('Build') {
            steps {
                script {
                    // Build your application here (e.g., run tests, linting, etc.)
                    echo 'Building the application...'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run your tests (if any)
                    echo 'Running tests...'
                    // Example: sh 'pytest'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy your application here
                    echo 'Deploying the application...'
                }
            }
        }
    }

    post {
        always {
            // Clean up the virtual environment after the build
            echo 'Cleaning up the environment...'
            sh 'rm -rf ${VENV_DIR}'
        }

        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}

