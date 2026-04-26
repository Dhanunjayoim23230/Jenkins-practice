pipeline {
    agent any

    environment {
        APP_NAME = 'my-app'
        BUILD_NUMBER = "${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code for ${APP_NAME}..."
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'echo "Build Stage - Running build commands"'
                // sh './build.sh'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Test Stage - Running unit tests"'
                // sh 'make check || true'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to production...'
                sh 'echo "Deploy Stage - Deployment in progress"'
                // sh './deploy.sh'
            }
        }
    }
    
    post {
        success {
            echo "Pipeline completed successfully for ${APP_NAME}"
        }
        failure {
            echo "Pipeline failed for ${APP_NAME}"
        }
    }
}


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
