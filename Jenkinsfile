pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Application started building...'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running tests...'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'code analysis...'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'security scanning...'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application...'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests...'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server...'
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Sending email notification...'
                mail (
                    subject: "Pipeline Notification: ${JOB_NAME} - Build #${BUILD_NUMBER}",
                    body: "The pipeline has completed. Check details at: ${BUILD_URL}",
                    to: 'gursharanpreetsinghsidhu38377@gmail.com'
                )
            }
        }
    }
}
