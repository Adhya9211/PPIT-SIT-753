pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = "/path/to/code/directory"
        TESTING_ENVIRONMENT = "TestingEnvironment"
        PRODUCTION_ENVIRONMENT = "ProductionEnvironment"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from ${env.DIRECTORY_PATH}" 
                echo "Compiling the code and generating necessary artifacts"
                
            }
        }
        
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"

            }
        }
        
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying the application to ${env.TESTING_ENVIRONMENT}"
            }
        }
        
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
