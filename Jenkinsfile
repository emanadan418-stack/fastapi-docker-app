pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/emanadan418-stack/fastapi-docker-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t fastapi-app:latest .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f fastapi-app || true'
                sh 'docker run -d -p 8000:8000 --name fastapi-app fastapi-app:latest'
            }
        }
    }
}

