pipeline {
    agent { label 'docker' }
    stages {
        stage('Example Build') {
            steps {
                sh 'df -h'
            }
        }
        stage('Check Ansible') {
            steps {
                sh 'ansible --version'
            }
        }
        stage('Run Ansible Test') {
            steps {
                sh 'ansible all -m ping'
            }
        }
    }
}
