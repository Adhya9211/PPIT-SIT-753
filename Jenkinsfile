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
                sh 'echo "Unit and Integration Tests logs" > logs.txt'
            }
            post {
                always {
                    archiveArtifacts artifacts: 'logs.txt', allowEmptyArchive: true
                    echo "Attaching logs.txt..."
                }
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Build Successful: Unit and Integration Tests',
                        body: 'The build was successful. Please find the attached test logs.',
                        attachmentsPattern: 'logs.txt'
                    )
                }
                failure {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Build Failed: Unit and Integration Tests',
                        body: 'The build failed. Please find the attached test logs.',
                        attachmentsPattern: 'logs.txt'
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
                sh 'echo "Security Scan logs" > security-scan.log'
            }
            post {
                always {
                    archiveArtifacts artifacts: 'security-scan.log', allowEmptyArchive: true
                }
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Build Successful: Security Scan',
                        body: 'The build was successful. Please find the attached security scan logs.',
                        attachmentsPattern: 'security-scan.log'
                    )
                }
                failure {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Build Failed: Security Scan',
                        body: 'The build failed. Please find the attached security scan logs.',
                        attachmentsPattern: 'security-scan.log'
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
                sh 'echo "Integration Tests on Staging logs" > staging-tests.log'
            }
            post {
                always {
                    archiveArtifacts artifacts: 'staging-tests.log', allowEmptyArchive: true
                }
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Integration Test Status',
                        body: 'Integration tests on staging environment were successful.',
                        attachmentsPattern: 'staging-tests.log'
                    )
                }
                failure {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Integration Test Status',
                        body: 'Integration tests on staging environment failed. Please find the attached logs.',
                        attachmentsPattern: 'staging-tests.log'
                    )
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
            post {
                success {
                    emailext (
                        to: 'adhyamehrotra9211@gmail.com',
                        from: 'nobody@nowhere',
                        subject: 'Build Status Email',
                        body: 'Build was successful! (Task 6.1C)'
                    )
                }
            }
        }
    }
}
