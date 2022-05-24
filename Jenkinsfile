pipeline {
    agent { label 'docker' }
    stages {
        stage('Example Build') {
            steps {
                sh 'df -h && ls -lh .'
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
                sh 'ls .'
            }
        }
        stage('Ansible Role Test') {
            steps {
                // sh 'ansible-playbook playbook.yml -vv'
            }
        }
    }
}
