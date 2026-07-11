pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/mohamedsala7320-sudo/simple-devops-project.git'
            }
        }

        stage('Build') {
            steps {
                dir('app') {
                    sh 'chmod +x mvnw'
                    sh './mvnw clean package'
                }
            }
        }
    }
}