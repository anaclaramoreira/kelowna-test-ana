pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Nothing to do!'
            sh 'ls -a'
		}
        }
        stage('Test') {
            steps {
                echo 'This is testing.'
            }
        }
        stage('Staging') {
            steps {
                echo 'This is Staging.'
            }
        }
        stage('Production') {
            steps {
                withCredentials([string(credentialsId: 'FIREBASE_TOKEN', variable: 'FIREBASE_TOKEN')]) {
            sh 'cat .firebaserc'
            sh 'firebase use production' 
            sh "firebase deploy --only hosting --token $FIREBASE_TOKEN"
                }
            }
        }
    }
}
