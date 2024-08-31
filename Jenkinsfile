pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nielmark/Jenkins_CICD.git']])
                sh 'docker build -t niel-test .'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker rm -f web-nginx && docker run -d --name web-nginx -p 8081:80 niel-test'
            }
        }
    }
}