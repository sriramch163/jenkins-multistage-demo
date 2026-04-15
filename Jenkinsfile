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
                echo "Building application..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Approval (PR only)') {
            when {
                changeRequest()
            }
            steps {
                input message: 'Approve this PR?', ok: 'Approve'
            }
        }

        stage('Deploy to Dev') {
            when {
                changeRequest()
            }
            steps {
                echo "Deploying to DEV..."
            }
        }

        stage('Deploy to Prod') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to PROD..."
            }
        }
    }
}