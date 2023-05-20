pipeline {
    agent any
    
    tools {docker 'docker'}
    
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
        stage('docker compose') {
            steps {
                sh '/usr/local/bin/docker-compose up -d'
            }
        }
    }
}
