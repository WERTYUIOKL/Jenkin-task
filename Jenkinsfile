pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Application started building...'
                    // Tool: Maven/Gradle
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running tests...'
                    // Tool: JUnit/pytest
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Running code analysis...'
                    // Tool: SonarQube
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Running security scanning...'
                    // Tool: OWASP Dependency Check/Snyk
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to staging...'
                    // Tool: Docker/Kubernetes
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging...'
                    // Tool: Selenium/pytest
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server...'
                    // Tool: Ansible/Docker/Kubernetes
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Sending email notification...'
                // Tool: Jenkins Mail Plugin
                mail (
                    subject: "Pipeline Notification: ${JOB_NAME} - Build #${BUILD_NUMBER}",
                    body: "The pipeline has completed. Check details at: ${BUILD_URL}",
                    to: 'akshitatri08@gmail.com'
                )
            }
        }
    }
}
