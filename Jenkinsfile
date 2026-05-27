pipeline{
    agent any
    tools {
        maven 'maven3'
    }
    environment {
        DOCKER_TAG = getVersion()
    }
    stages{
        stage('SCM'){
            steps{
                git 'https://github.com/Manash2712/Docker-Ansible-Jenkins'
            }
        }
        stage('Maven Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Docker Build'){
            steps{
                sh "docker build . -t manashchauhan/jenkinsansible:${DOCKER_TAG} "
            }
        }
    }
}

def getVersion(){
    def commitHash = sh returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}
