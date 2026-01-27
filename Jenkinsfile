pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    environment {
        MAVEN_HOME = tool 'Maven-3'
        PATH = "${env.MAVEN_HOME}/bin;${env.PATH}"
    }

    stages {

        stage('Build & Test - Main') {
            when {
                branch 'main'
            }
            steps {
                echo 'Running full CI pipeline for MAIN branch'
                bat 'mvn.cmd clean package'
            }
        }

        stage('Test Only - Feature Branch') {
            when {
                branch 'feature/login'
            }
            steps {
                echo 'Running tests only for FEATURE branch'
                bat 'mvn.cmd test'
            }
        }

        stage('Test & Security Scan - Release Branch') {
            when {
                branch 'release/v1.0'
            }
            steps {
                echo 'Running tests and security scan for RELEASE branch'
                bat 'mvn.cmd test'
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
