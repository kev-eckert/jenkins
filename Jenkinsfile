pipeline {
    agent any
    
    environment {
        // Variables d'environnement globales
        MY_ENV_VAR = 'production'
        SECRET = credentials('secret')  // Utilise le credential 'secret'
    }
    
    stages {
        stage('Build') {
            agent {
                kubernetes 'alpine:latest'
            }
            steps {
                echo 'Building..'
                sh 'whoami'
                sh 'echo SECRET : ${SECRET}'
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
