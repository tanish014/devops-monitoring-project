pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/tanish014/devops-monitoring-project.git'
            }
        }

        stage('Check Docker') {
            steps {
                sh '/usr/bin/docker --version || which docker'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '/usr/bin/docker build -t devops-monitoring-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '/usr/bin/docker run -d -p 3000:3000 devops-monitoring-app'
            }
        }
    }
}