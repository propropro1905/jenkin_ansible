pipeline {
    agent any
    
    stages {
        stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
                }
            }
        }
        stage("deploy"){
            steps{
                ansiblePlaybook installation: 'Ansible', inventory: 'hosts', playbook: 'docker.yaml'
            }
        }
    }
}