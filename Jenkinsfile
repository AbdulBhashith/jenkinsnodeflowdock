pipeline {
    agent any
    tools {
        dockerTool "docker"
    }
    stages {
        stage('git clone') {
            steps {
               git branch: 'main', url: 'https://github.com/AbdulBhashith/jenkinsnodeflowdock'
            }
        }
        stage('version') {
            steps {
                sh 'docker --version'
                sh 'docker info'
            }
        }
        stage('Check Docker Compose Version') {
              steps {
                sh 'docker-compose --version'
              }
            }
        stage('Run Docker Compose') {
              steps {
                sh 'docker-compose up -d'
              }
            }
    }
}
