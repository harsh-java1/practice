
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checkout is handled by Jenkins SCM.'
            }
        }

        stage('Build and Test') {
            steps {
                sh 'chmod +x mvnw'
                sh './mvnw clean verify'
            }
        }

        stage('Archive JAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar',
                                 fingerprint: true
            }
        }
    }
}
