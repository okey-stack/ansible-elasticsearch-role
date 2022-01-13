pipeline {
    agent {
      label 'ansible'
    }
    stages{
        stage('Git checkout') {
            steps {
                sh 'mkdir ansible-elasticsearch-role'
                sh 'cd ansible-elasticsearch-role'
                git branch: 'main', credentialsId: '23dc5dd6-568b-4238-a10d-3b6a780fda1d', url: 'git@github.com:okey-stack/ansible-elasticsearch-role.git'
            }
        }
        stage('Install molecule') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run molecule') {
            steps {
                sh 'molecule test'
            }
        }
    }
}