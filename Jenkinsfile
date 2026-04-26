pipeline {
    // Run on any available agent
    agent any

    // Define environment variables
    environment {
        APP_NAME = 'my-app'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM (default in Jenkins)
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                // sh './build.sh'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // sh 'make check || true' // Allows JUnit to process failures
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // sh './deploy.sh'
            }
        }
    }

    // Post-build actions (notifications, cleanup)
    post {
        always {
            echo 'Cleaning up...'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
