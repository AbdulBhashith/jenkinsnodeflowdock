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
            }
        }
        stage('Install Docker Compose') {
              steps {
                sh 'curl -L https://github.com/docker/compose/releases/download/<DOCKER_COMPOSE_VERSION>/docker-compose-<OS>-<ARCH> -o /usr/local/bin/docker-compose'
                sh 'chmod +x /usr/local/bin/docker-compose'
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
