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
        stage('docker compose') {
            steps {
                step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'ExecuteCommandInsideContainer', command: 'docker-compose up -d', index: 1, privilegedMode: false, service: 'nodekeeper', workDir: '/var/jenkins_home/workspace/NodePipeline/'], useCustomDockerComposeFile: false])
            }
        }
    }
}
