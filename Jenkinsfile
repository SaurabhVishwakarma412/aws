pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling code from repository'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
                sh 'echo Build Started'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'echo Tests Running'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh 'echo Deployment Done'
            }
        }
    }
}