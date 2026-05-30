pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t aws-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
docker stop aws-container
docker rm aws-container
docker run -d --name aws-container -p 5001:5000 aws-app
'''
            }
        }
    }
}