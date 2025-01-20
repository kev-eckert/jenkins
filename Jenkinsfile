pipeline {
    agent any
    
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
                sh 'echo ${MY_ENV_VAR}'
                sh 'echo SECRET : ${SECRET}'
                sh 'cat /etc/os-release'
                runUnitTests()
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

def runUnitTests() {
   // executes tests
  sh 'echo run unit tests...'
}
