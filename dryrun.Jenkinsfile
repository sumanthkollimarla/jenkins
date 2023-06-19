pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'MINUTES')
    }
    tools {
            maven 'maven-3.5.0'
        }
    stages {
        stage('Parallel') {
            parallel {
            stage('First Stage Name') {
                steps {
                    sh "hostname"   
                    sh 'mvn --version'
                    sh "echo One"
                    sh "env"
                    sh "sleep 10"
                }
            }
            stage('Second Stage Name') {
                steps {
                    sh "echo One"
                    sh "echo ENV_URL is ${ENV_URL}"
                    sh "echo $ACCESS_KEY"
                    sh "sleep 20"
                }
            }
            stage('Third Stage Name') {
                environment {
                    ENV_URL = "stage.google.com"
                }
                steps {
                    sh "echo ENV_URL is ${ENV_URL}"
                    sh "sleep 21"
                    }
                }
            }    
        }
    }
}