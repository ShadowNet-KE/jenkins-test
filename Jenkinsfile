pipeline {
    agent { label 'docker' }
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
        stage('Bootstrap') {
            steps {
                sh 'python -m pip install -r requirements.txt'
                sh 'ansible-galaxy install -r requirements.yml'
                sh 'ansible-playbook playbook.yml -vv'
            }
        }
    }
}
