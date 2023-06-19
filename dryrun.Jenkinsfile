pipeline {
    agent any

    options {
        ansiColor('xterm')
    }
     environment {
        
        SSH_CRED = credentials('SSH-CRED')
    }
    tools {
            maven 'maven-3.5.0'
        }
    stages {

            stage('performing ansible dryrun') {
                steps {
                    sh "ansible-playbook robot-dryrun.yml -e COMPONENT=mongodb -e ENV=dev -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW}"
                    
                }
            }
        }    
    }
