pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build stage is running'
                echo 'Command: mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests'
                echo 'Command: mvn unit test'
                echo 'Command: mvn integration test'
            }
                post {
        failure {
            // to send the email notifications if test stage fails
            emailext attachLog: true,
                subject: 'Failure of the Testing stage',
                   body: 'The unit and integration tests resulted in a failure!',
                     to: '7136tejasri@gmail.com'
        }
        success {
            // to send the email notifications if test stage succeeds
            emailext attachLog: true,
                subject: 'Success of the Testing stage',
                   body: 'The unit and integration tests resulted in a success!',
                     to: '7136tejasri@gmail.com'
        }
    }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code analysis stage is running'
                echo 'Command: sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scan stage is running'
                echo 'Command: command for security scan'
            }
                post {
        failure {
            // to send the email notifications if scan stage fails
            emailext attachLog: true,
                subject: 'Failure of the security scan stage',
                   body: 'The security scan stage resulted in a failure!',
                     to: '7136tejasri@gmail.com'
        }
        success {
            // to send the email notifications if scan stage succeeds
            emailext attachLog: true,
                subject: 'Success of the security scan stage',
                   body: 'The security scan stage resulted in a success!',
                     to: '7136tejasri@gmail.com'
        }
    }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment is being run'
                echo 'Command: deploy-to-stageing-command'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment.'
                echo 'Command: staging-integration-test-command'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'The deploy to production stage is running'
                echo 'Command: deploy to production command'
            }
        }
    }
}

