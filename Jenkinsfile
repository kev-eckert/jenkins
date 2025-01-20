pipeline {
    agent any
    
    environment {
        // Variables d'environnement globales
        MY_ENV_VAR = 'production'
    }
    
    stages {
        stage('Build') {
            agent {
                docker 'alpine:latest'
            }
            steps {
                echo 'Building..'
                sh 'whoami'
                sh 'cat /etc/os-release'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
