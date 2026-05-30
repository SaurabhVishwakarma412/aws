pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/SaurabhVishwakarma412/aws.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t aws-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop aws-container || true
                docker rm aws-container || true

                docker run -d \
                  --name aws-container \
                  -p 5001:5000 \
                  aws-app
                '''
            }
        }
    }
}