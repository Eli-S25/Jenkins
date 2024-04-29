pipeline {
    agent any
    
    stages {
        stage("Build") {
            steps {
                echo "Simulating building the code using Maven"
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Simulating running unit tests"
                echo "Simulating running integration tests"
            }
        post {
        success {
           mail to: "elie246na@gmail.com",
            subject: "Integration test",
            body: "Integraton test was successful"
        }
        failure {
            mail to: "elie246na@gmail.com",
            subject: "Integration test",
            body: "Integration Test has failed"
        }
        
        stage('Code Analysis') {
            steps {
                echo "Simulating integrating code analysis tool (e.g., SonarQube)"
                echo "Simulating running SonarQube scanner"
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Simulating performing security scan using OWASP ZAP or SonarQube"
            }
        post {
        success {
           mail to: "elie246na@gmail.com",
            subject: "Security Scan",
            body: "Security scan was successful"
        }
        failure {
            mail to: "elie246na@gmail.com",
            subject: "Security scan",
            body: "Security scan failed"
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Simulating deploying the application to staging server"
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo "Simulating running integration tests on staging environment"
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploy the application to production server (e.g., AWS EC2)"
            }
        }
    }
}
        }
    }
}
