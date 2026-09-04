pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Building the application...'
                echo 'Tool: Maven - compiles source code and packages it into a JAR/WAR artifact'
                bat 'echo mvn clean package (mock)'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Running automated tests...'
                echo 'Tools: JUnit for unit tests, Selenium/Postman for integration tests'
                bat 'echo mvn test (mock)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Analysing code quality against industry standards...'
                echo 'Tool: SonarQube / SonarCloud - checks code smells, duplication, maintainability'
                bat 'echo sonar-scanner (mock)'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Scanning for known vulnerabilities...'
                echo 'Tool: Snyk / Trivy / OWASP Dependency-Check'
                bat 'echo snyk test (mock)'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploying to staging server...'
                echo 'Tool: Ansible / AWS EC2 via SSH - copies artifact to a staging EC2 instance'
                bat 'echo ansible-playbook deploy-staging.yml (mock)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Running integration tests in the staging environment...'
                echo 'Tool: Postman/Newman or Selenium against the staging URL'
                bat 'echo newman run staging-tests.json (mock)'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploying to production server...'
                echo 'Tool: AWS CodeDeploy / Ansible / Docker to a production EC2 instance'
                bat 'echo deploy to production EC2 (mock)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
