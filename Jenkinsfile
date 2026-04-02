pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/LondheShubham153/django-notes-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t notes-app .'
            }
        }

        stage('Run') {
            steps {
                sh '''
                docker stop notes-app || true
                docker rm notes-app || true
                docker run -d -p 8000:8000 notes-app
                '''
            }
        }
    }
}
