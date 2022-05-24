pipeline {
    agent { label 'docker' }
    options {
        ansiColor('xterm')
    }
    stages {
        stage('Check Ansible') {
            steps {
                sh 'ansible --version'
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
        stage('Prepare') {
            steps {
                sh 'python -m pip install -r requirements.txt'
                sh 'ansible-galaxy install -r requirements.yml'
            }
        }
        stage('Converge') {
            steps {
                sh 'ansible-playbook playbook.yml -vv'
            }
        }
        stage('NPM Test') {
            steps {
                sh 'npm --version'
                sh 'node --version'
            }
        }
    }
}
