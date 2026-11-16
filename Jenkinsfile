
pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
                echo 'Source code checked out'
            }
        }

        stage('Build') {
            steps {
                bat '.\\mvnw.cmd clean compile'
            }
        }

        stage('Test') {
            steps {
                bat '.\\mvnw.cmd test'
            }
        }

        stage('Package') {
            steps {
                bat '.\\mvnw.cmd package -DskipTests'
            }
        }

    }

    post {
        success {
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}

