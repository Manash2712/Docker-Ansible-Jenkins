pipeline{
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage('SCM'){
            steps{
                git 'https://github.com/Manash2712/Docker-Ansible-Jenkins'
            }
        }
        stage('Maven build'){
            steps{
                sh "mvn clean package"
            }
        }
    }
}
