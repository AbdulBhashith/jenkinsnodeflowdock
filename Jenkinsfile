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
                sh 'docker-compose up'
            }
        }
    }
}
