pipeline {

    agent any

    environment {
        IMAGE_NAME = "student-devops-app"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/Priyanshu16072005/CI-CD_Jenkins'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Show Docker Images') {
            steps {
                sh 'docker images'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 4000:3000 student-devops-app'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Executed Successfully'
        }
        failure {
            echo 'Pipeline Failed'
        }
    }
}