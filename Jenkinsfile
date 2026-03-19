pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Abhinandabb/Helm-practise'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t helmk8 .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push abhinand121/helmk8:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f Deployment.yaml'
                sh 'kubectl apply -f Service.yaml'
            }
        }
    }
}