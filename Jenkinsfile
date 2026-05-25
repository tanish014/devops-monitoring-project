pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
              git branch: 'main', url: 'https://github.com/tanish014/devops-monitoring-project.git'            }
        }

        stage('Check Docker') {
            steps {
               sh 'docker --version'             }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-monitoring-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '/usr/bin/docker stop devops-monitoring-app || true'
                sh '/usr/bin/docker rm devops-monitoring-app || true'
                sh '/usr/bin/docker run -d --name devops-monitoring-app -p 3000:3000 devops-monitoring-app'
            }
        }
    }
}