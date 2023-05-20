pipeline {
    agent any

    stages {
        stage('git clone') {
            steps {
               git branch: 'main', url: 'https://github.com/AbdulBhashith/jenkinsnodeflowdock'
            }
        }
        stage('docker compose') {
            steps {
                sh '/usr/local/bin/docker-compose up -d'
            }
        }
    }
}
