pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t niel-test .'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -d --name web-nginx -p 8081:80 niel-test'
            }
        }
    }
}