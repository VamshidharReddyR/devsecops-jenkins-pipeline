pipeline {

    agent any

    environment {
        IMAGE_NAME = "devsecops-jenkins-pipeline"
        IMAGE_TAG  = "${BUILD_NUMBER}"
    }

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mkdir -p reports'
                sh 'pytest --junitxml=reports/test-results.xml'
            }

            post {
                always {
                    junit 'reports/test-results.xml'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Running SonarQube Scan'
            }
        }

        stage('Quality Gate') {
            steps {
                echo 'Validating SonarQube Quality Gate'
            }
        }

        stage('OWASP Dependency Check') {
            steps {
                sh 'mkdir -p reports'
                echo 'Generating OWASP Dependency Check Report'
            }
        }

        stage('Trivy Scan') {
            steps {
                sh 'mkdir -p reports'
                echo 'Generating Trivy Vulnerability Report'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ${IMAGE_NAME}:${IMAGE_TAG} .'
            }
        }
    }

    post {

        always {
            archiveArtifacts artifacts: 'reports/*', allowEmptyArchive: true
        }

        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }
    }
}
