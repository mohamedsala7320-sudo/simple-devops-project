pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Repository already cloned by Jenkins'
            }
        }

        stage('Build Application') {
            steps {
                dir('app') {
                    bat '.\\mvnw.cmd clean package'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('app') {
                    bat 'docker build -t mosala7320/springboot-demo:v1 .'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push mosala7320/springboot-demo:v1'
            }
        }

        stage('Deploy To Kubernetes') {
            steps {
                bat 'kubectl apply -f kubernetes\\deployment.yaml'
                bat 'kubectl apply -f kubernetes\\service.yaml'
                bat 'kubectl rollout restart deployment springboot-demo'
            }
        }
    }
}