pipeline {
    agent any
    
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
            }
        }
        
        stage('Production') {
            steps {
                echo 'Deploying to production...'
                sh 'firebase use production'
                sh 'firebase deploy --only hosting:production'
                echo 'Production deployment completed!'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed for Ana Clara Moreira Araujo'
        }
        success {
            echo 'Deployment successful! Check: https://kelowna-production-79.web.app'
        }
        failure {
            echo 'Pipeline failed! Check logs for details.'
        }
    }
}
