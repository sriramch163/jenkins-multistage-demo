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
                echo "Building PR..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }
    }
}