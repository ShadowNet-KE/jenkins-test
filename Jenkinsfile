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
        stage('Checkout Role') {
            steps {
                git branch: 'main',
                url: 'https://github.com/buluma/ansible-playbook-zabbix.git'
                sh 'ls -lh'
                sh 'ansible-galaxy collection install buluma.roles'
            }
        }
        stage('Ansible Role Test') {
            steps {
                sh 'ansible-galaxy install -r roles/requirements.yml'
                sh 'ansible-playbook playbook.yml -vv'
            }
        }
    }
}
