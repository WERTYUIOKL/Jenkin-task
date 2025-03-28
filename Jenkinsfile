pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Application started building...'
                    // Tool: Maven/Gradle
                    sh 'mvn clean package' // For Java projects
                    // sh './gradlew build' // For Gradle projects
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running tests...'
                    // Tool: JUnit/pytest
                    sh 'mvn test' // Java projects with JUnit
                    // sh 'pytest tests/' // Python projects
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Running code analysis...'
                    // Tool: SonarQube
                    sh 'sonar-scanner -Dsonar.projectKey=my_project'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Running security scanning...'
                    // Tool: OWASP Dependency Check/Snyk
                    sh 'dependency-check --scan ./'
                    // sh 'snyk test' // If using Snyk
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to staging...'
                    // Tool: Docker/Kubernetes
                    sh 'kubectl apply -f staging-deployment.yaml'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging...'
                    // Tool: Selenium/pytest
                    sh 'pytest integration_tests/'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server...'
                    // Tool: Ansible/Docker/Kubernetes
                    sh 'kubectl apply -f production-deployment.yaml'
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
