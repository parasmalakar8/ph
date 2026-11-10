pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website:latest .'
            }
        }
        stage('Run Website') {
            steps {
                sh 'docker rm -f my-website || true'
                sh 'docker run -d -p 8081:80 --name my-website my-website:latest'
            }
        }
    }
}