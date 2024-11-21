pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:$PATH"  // Ensure Python and pip are in the PATH
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Install dependencies
                    sh 'python3 -m pip install --upgrade pip'
                    sh 'python3 -m pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run your tests here
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Your deploy steps here
                }
            }
        }
    }
}

