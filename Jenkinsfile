
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm ci'
            }
        }

        stage('Code Quality') {
            steps {
                bat 'npm run lint'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
    }

    post {
        success {
            echo 'News Analysis application built successfully.'
        }
        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}
