pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = 'https://github.com/WERTYUIOKL/Jenkin-task/new/main' 
        TESTING_ENVIRONMENT = 'task'
        PRODUCTION_ENVIRONMENT = 'akshit' 
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }
        
        stage('Test') {
            steps {
                echo "Running Unit tests"
                echo "Running Integration tests"
            }
        }
        
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploy the application to the testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS') // Simulate manual approval with a 10-second pause
                echo "Approval received. Proceeding to production deployment."
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
