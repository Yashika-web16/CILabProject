pipeline {
    agent any

    stages {

        stage('Build & Test - Main') {
            when { branch 'main' }
            steps {
                echo 'Running full CI pipeline for MAIN branch'
                bat '"C:\\ProgramData\\Jenkins\\.jenkins\\tools\\hudson.tasks.Maven_MavenInstallation\\Maven-3\\bin\\mvn.cmd" clean package'
            }
        }

        stage('Test Only - Feature Branch') {
            when { branch 'feature/login' }
            steps {
                echo 'Running tests only for FEATURE branch'
                bat '"C:\\ProgramData\\Jenkins\\.jenkins\\tools\\hudson.tasks.Maven_MavenInstallation\\Maven-3\\bin\\mvn.cmd" test'
            }
        }

        stage('Test & Security Scan - Release Branch') {
            when { branch 'release/v1.0' }
            steps {
                echo 'Running tests and security scan for RELEASE branch'
                bat '"C:\\ProgramData\\Jenkins\\.jenkins\\tools\\hudson.tasks.Maven_MavenInstallation\\Maven-3\\bin\\mvn.cmd" test'
                echo 'Security scan simulated'
            }
        }
    }

    post {
        success { echo 'Build successful' }
        failure { echo 'Build failed' }
    }
}
