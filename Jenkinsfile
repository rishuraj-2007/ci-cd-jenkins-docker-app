pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Build') {
            steps {
                echo "Installing dependencies..."
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                bat 'echo No tests defined'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t my-ci-cd-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker stop my-container || exit 0'
                bat 'docker rm my-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name my-container my-ci-cd-app'
            }
        }
    }
}