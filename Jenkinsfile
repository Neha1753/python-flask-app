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
                    // Install Python 3 and pip if not installed
                    sh 'python3 --version || sudo apt-get install python3 python3-pip -y'
                    
                    // Create a virtual environment in the 'venv' directory
                    sh 'python3 -m venv ${VENV_DIR}'
                    
                    // Activate the virtual environment and install dependencies from requirements.txt
                    sh '''
                        source ${VENV_DIR}/bin/activate
                        pip install --upgrade pip
                        pip install -r requirements.txt
                    '''
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

