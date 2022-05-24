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
//         stage('Checkout Role') {
//             steps {
//                 git branch: 'main',
//                 url: 'https://github.com/buluma/ansible_workstation.git'
//                 sh 'ls -lh'
//                 sh 'ansible-galaxy collection install buluma.workstation'
//             }
//         }
        stage('Ansible Role Test') {
            steps {
                sh 'ansible-galaxy install -r requirements.yml'
                sh 'ansible-playbook playbook.yml -vv'
            }
        }
    }
}
