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
                script {
                  def dockerComposeVersion = '1.29.1'
                  def os = 'linux'
                  def arch = 'amd64'
                  def dockerComposeUrl = "https://github.com/docker/compose/releases/download/${dockerComposeVersion}/docker-compose-${os}-${arch}"

                  sh "sudo curl -L ${dockerComposeUrl} -o /usr/local/bin/docker-compose"
                  sh "sudo chmod +x /usr/local/bin/docker-compose"
                }
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
