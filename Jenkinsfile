pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

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
                expression { env.BRANCH_NAME.startsWith('feature') }
            }
            steps {
                echo 'Running tests only for FEATURE branch'
                bat 'mvn test'
            }
        }

        stage('Test & Security Scan - Release Branch') {
            when {
                expression { env.BRANCH_NAME.startsWith('release') }
            }
            steps {
                echo 'Running tests and security scan for RELEASE branch'
                bat 'mvn test'
                echo 'Security scan simulated'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Build successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
