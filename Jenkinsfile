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
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment is being run'
                echo 'Command: deploy-to-stageing-command'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
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

    post {
        failure {
            // to send the email notifications if pipeline fails
            emailtext attachlog: true,
                subject: "Failure of the Pipeline",
                   body: "The jenkins pipeline resulted in a failure!",
                     to: '7136tejasri@gmail.com'
        }
        success {
            // to send the email notifications if pipeline succeeds
            emailtext attachlog: true,
                subject: "Success of the Pipeline",
                   body: "The jenkins pipeline resulted in a success!",
                     to: '7136tejasri@gmail.com'
        }
    }
}

