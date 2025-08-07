pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/analytics-jiten/devops-assignment2'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('devops-assignment-website')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f static-site || true'
                sh 'docker run -d --name static-site -p 8081:80 devops-assignment-website'
            }
        }
    }
}
