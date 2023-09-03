pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the code using Maven..."
                    // Use Maven to compile and package the code
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo "Running unit tests using JUnit..."
                    // Use JUnit or another test automation tool for unit tests

                    echo "Running integration tests using Selenium..."
                    // Use a tool like Selenium or JUnit for integration tests
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
                    echo "Running code analysis using SonarQube..."
                    // Integrate a code analysis tool (e.g., SonarQube) using Jenkins plugins
                     }
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    echo "Performing security scan..."
                    // Integrate a security scanning tool (e.g., OWASP ZAP) using Jenkins plugins
                }
            }
    post {
       
        failure {
            script {
                echo "Sending notification email about failure..."
                emailext body: "Pipeline failed. Check logs for details.",
                         subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                         to: "valour2417@gmail.com"
            }
        }
        success {
            script {
                echo "Sending notification email about success..."
                emailext body: "Pipeline succeeded. Logs attached.",
                         subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                         to: "valour2417@gmail.com"
            }
        }
    }

        }

        stage('Deploy to Staging') {
            steps {
                script {
                    echo "Deploying to staging server (e.g., AWS EC2 instance)..."
                    // Use a deployment script or tool to deploy to staging
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo "Running integration tests on staging..."
                    // Use the same test automation tools as earlier to run integration tests on staging
                }
            }
   post {
        always {
            // Archive logs as artifacts
            archiveArtifacts artifacts: '**/logs/*', allowEmptyArchive: true
        }
        failure {
            script {
                echo "Sending notification email about failure..."
                emailext body: "Pipeline failed. Check logs for details.",
                         subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                         to: "valour2417@gmail.com"
            }
        }
        success {
            script {
                echo "Sending notification email about success..."
                emailext body: "Pipeline succeeded. Logs attached.",
                         subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                         to: "valour2417@gmail.com"
            }
        }
    }

        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo "Deploying to production server (e.g., AWS EC2 instance)..."
                    // Use a deployment script or tool to deploy to production
                }
            }
        }
    }
}
