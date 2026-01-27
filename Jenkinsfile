pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    stages {
        stage('Build & Test - Main') {
            when {
                branch 'main'
            }
            steps {
                echo 'Running full CI pipeline for MAIN branch'
                bat 'mvn clean package'
            }
        }

        stage('Test Only - Feature Branch') {
            when {
                branch 'feature/login'
            }
            steps {
                echo 'Running tests only for FEATURE branch'
                bat 'mvn test'
            }
        }

        stage('Test & Security Scan - Release Branch') {
            when {
                branch 'release/v1.0'
            }
            steps {
                echo 'Running tests and security scan for RELEASE branch'
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
