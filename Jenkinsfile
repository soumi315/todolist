pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Use Maven wrapper if available
                script {
                    def mvnCmd = bat(script: 'mvnw -v', returnStatus: true)
                    if (mvnCmd == 0) {
                        sh './mvnw clean package'
                    } else {
                        sh 'mvn clean package'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                // Use Maven wrapper if available
                script {
                    def mvnCmd = bat(script: 'mvnw -v', returnStatus: true)
                    if (mvnCmd == 0) {
                        sh './mvnw test'
                    } else {
                        sh 'mvn test'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // Use platform-independent script execution
                bat './deploy.bat'
            }
        }
    }
}
