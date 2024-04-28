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
                echo "Perform security scan using OWASP ZAP or SonarQube"
               echo Example:
                echo sh 'owasp-zap -cmd -quickurl http://localhost:8080/myapp'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo Deploy the application to staging server (e.g., AWS EC2)
                echo Example:
                echo sh 'ansible-playbook deploy-staging.yml'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
            echo Run integration tests on staging environment
                echo Example:
                echo sh 'mvn integration-test'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo Deploy the application to production server (e.g., AWS EC2)
                echo Example:
                echo sh 'ansible-playbook deploy-production.yml'
            }
        }
    }
    
    post {
        success {
            echo Send success notification email
            echo Example:
            echo emailext body: "Pipeline succeeded",
            echo     subject: "Pipeline Success",
            echo     to: "s223361196@deakin.edu.au"
        }
        failure {
            echo Send failure notification email with logs as attachment
            echo Example:
            echo emailext attachLog: true,
            echo     body: "Pipeline failed",
            echo     subject: "Pipeline Failure",
            echo     to: "s223361196@deakin.edu.au"
        }
    }
}
