pipeline {

    agent any

    environment {
        IMAGE = "krixh007/mlops-app"
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Krixh0003/mlops-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name mlops-container $IMAGE || true'
            }
        }
    }
}
