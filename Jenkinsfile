pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/tanish014/devops-monitoring-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-monitoring-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 3000:3000 devops-monitoring-app'
            }
        }
    }
}