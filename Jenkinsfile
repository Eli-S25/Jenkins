pipeline {
    agent any
    
    stages {
        stage("Build") {
            steps {
                // Build the code using Maven
                sh 'mvn clean package'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests
                sh 'mvn test'
                // Run integration tests
                sh 'mvn integration-test'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Integrate code analysis tool (e.g., SonarQube) /n"
                echo "This step might involve running SonarQube scanner"
                echo "Example:"
                echo sh 'sonar-scanner'
            }
        }
        
        stage('Security Scan') {
            steps {
                // Perform security scan using OWASP ZAP or SonarQube
                // Example:
                // sh 'owasp-zap -cmd -quickurl http://localhost:8080/myapp'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                // Deploy the application to staging server (e.g., AWS EC2)
                // Example:
                // sh 'ansible-playbook deploy-staging.yml'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
                // Example:
                // sh 'mvn integration-test'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                // Deploy the application to production server (e.g., AWS EC2)
                // Example:
                // sh 'ansible-playbook deploy-production.yml'
            }
        }
    }
    
    post {
        success {
            // Send success notification email
            // Example:
            // emailext body: "Pipeline succeeded",
            //     subject: "Pipeline Success",
            //     to: "email@example.com"
        }
        failure {
            // Send failure notification email with logs as attachment
            // Example:
            // emailext attachLog: true,
            //     body: "Pipeline failed",
            //     subject: "Pipeline Failure",
            //     to: "email@example.com"
        }
    }
}
