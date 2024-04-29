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
    
    post {
        success {
           mail to: "elie246na@gmail.com",
            subject: "Build Status Email",
            body: "Build was successful"
        }
        failure {
            mail to: "elie246na@gmail.com",
            subject: "Build Status Email",
            body: "Build was successful"
        }
    }
}

