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
                sh 'go build -o hello-world main.go'
            }
        }
        
        stage('Test') {
            steps {
                sh 'go test ./...'
            }
        }
        
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'hello-world'
            }
        }
    }
}
