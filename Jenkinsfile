pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "/path/to/code"
        TESTING_ENVIRONMENT = "TestingEnvironment"
        PRODUCTION_ENVIRONMENT = "VamikaProduction"
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetching source code from directory: ${DIRECTORY_PATH}"
                echo "Compiling the code and generating artifacts"
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
                echo "Deploying the application to ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                script {
                    echo "Waiting for manual approval..."
                    sleep(time: 10, unit: 'SECONDS')
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
