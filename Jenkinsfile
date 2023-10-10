pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout code from Git
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build your application (e.g., Maven, npm)
                    sh 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy your application (e.g., copy files, deploy to server)
                    sh './deploy.sh'
                }
            }
        }
    }
}
