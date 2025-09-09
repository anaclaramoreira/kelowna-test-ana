pipeline {
    agent any
    environment {
        GOOGLE_APPLICATION_CREDENTIALS = credentials('firebase-service-account')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                echo 'Project: Kelowna Trails - Ana Clara Moreira Araujo'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                echo 'This is testing.'
            }
        }
        stage('Staging') {
            steps {
                echo 'This is Staging.'
                echo 'Staging environment ready.'
                sh 'firebase use staging'
                sh 'firebase deploy --only hosting'
            }
        }
        stage('Production') {
            steps {
                echo 'Deploying to production...'
                sh 'firebase use production'
                sh 'firebase deploy --only hosting'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed for Ana Clara Moreira Araujo'
        }
        failure {
            echo 'Pipeline failed! Check logs for details.'
        }
    }
}
