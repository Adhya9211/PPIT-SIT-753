pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build the code using a build automation tool like Maven
                echo "Building the code using Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests using a test automation tool like JUnit
                // Run integration tests using a test automation tool like Selenium or Cucumber
                echo "Running unit tests and integration tests"
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate a code analysis tool like SonarQube or Checkstyle
                echo "Running code analysis with SonarQube or Checkstyle"
            }
        }
        stage('Security Scan') {
            steps {
                // Perform a security scan on the code using a security scanning tool like OWASP ZAP
                echo "Performing security scan with OWASP ZAP"
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy the application to a staging server (e.g., AWS EC2 instance)
                echo "Deploying to staging server"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on the staging environment
                echo "Running integration tests on staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy the application to a production server (e.g., AWS EC2 instance)
                echo "Deploying to production server"
            }
        }
        stage('Complete') {
            steps {
                echo "Completed"
            }
            post{
                success{
                    mail to: "adhyamehrotra9211@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successfull!(Task 6.1C)"
               }
           }
       }
         
    }
 }
