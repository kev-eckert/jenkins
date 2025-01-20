pipeline {
  agent {
    kubernetes {
      defaultContainer 'alpine:latest'
      yamlFile 'KubernetesPod.yaml'
    }
  }
    
//pipeline {
//    agent any
    
    environment {
        // Variables d'environnement globales
        MY_ENV_VAR = 'production'
        SECRET = credentials('secret')  // Utilise le credential 'secret'
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'whoami'
                sh 'echo SECRET : ${SECRET} > /tmp/secret'
                sh 'cat /tmp/secret'
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
