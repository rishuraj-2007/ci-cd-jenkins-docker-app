pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/rishuraj-2007/ci-cd-jenkins-docker-app.git'
            }
        }

        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t my-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker stop my-container || exit 0'
                bat 'docker rm my-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name my-container my-app'
            }
        }
    }
}