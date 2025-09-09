// NOTE for Students: 


// In this example, Firebase is being used directly without credentials. 
// For real projects (production CI/CD), you must NOT hardcode Firebase 
// login. 
// Instead, store your Firebase token or service account key in Jenkins 
// Credentials 
// (e.g., "Secret Text" or "Secret File") and load it as an environment 
// variable. 
// Example: withCredentials([string(credentialsId: 'FIREBASE_TOKEN', 
// variable: 'FIREBASE_TOKEN')]) { ... } 
// Then run: sh "firebase deploy --token $FIREBASE_TOKEN"
//


pipeline {
    agent any


    stages {
        
	stage('Build') {
            steps {
                echo 'Nothing to do!' 
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
                sh 'firebase use production'
                sh 'firebase deploy --only hosting'
            }
        }
    }
}

