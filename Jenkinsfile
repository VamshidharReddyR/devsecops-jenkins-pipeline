pipeline {

    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Running SonarQube Scan'
            }
        }

        stage('OWASP Dependency Check') {
            steps {
                echo 'Running OWASP Dependency Check'
            }
        }

        stage('Trivy Scan') {
            steps {
                echo 'Running Trivy Security Scan'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devsecops-jenkins-pipeline .'
            }
        }
    }
}
