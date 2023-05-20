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
        stage('check block') {
            steps {
                step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: false])
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
