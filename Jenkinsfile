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
              post {
                always {
                    sh"touch logs.txt..."
                    echo "Attaching logs.txt..."
                }
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'ashu123@gmail.com'
                        subject: 'Build Successful: Unit and Integration Tests',
                        body: 'The build was successful. Please find the attached test logs.',
                        attachLog: true
                        attachmentsPattern: "**/logs.txt"
                    )
                }
                failure {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'ashu123@gmail.com'
                        subject: 'Build Failed: Unit and Integration Tests',
                        body: 'The build failed. Please find the attached test logs.',
                        attachLog: true  
                        attachmentsPattern: "**/logs.txt"
                        
                    )
                }
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
            post {
                always {
                    archiveArtifacts artifacts: '**/security-scan-*.log', allowEmptyArchive: true
                }
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        subject: 'Build Successful: Security Scan',
                        body: 'The build was successful. Please find the attached security scan logs.',
                        attachLog: true
                    )
                }
                failure {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        subject: 'Build Failed: Security Scan',
                        body: 'The build failed. Please find the attached security scan logs.',
                        attachLog: true
                    )
                }
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
            post {
                always {
                    sh "Attaching logs.txt"
        }
                success {
                    mail to: "${EMAIL}",
                    subject: "Integration Test Status",
                    body: "Tests failed!"
                }
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
