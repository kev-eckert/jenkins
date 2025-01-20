pipeline {
    agent any
    
    environment {
        // Variables d'environnement globales
        MY_ENV_VAR = 'production'
        SECRET = credentials('secret')  // Utilise le credential 'secret'
    }
    
    stages {
        stage('Installing kubectl') {
            steps {
                sh 'curl -LO https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl'
                sh 'chmod +x ./kubectl'
                sh '$(pwd)/kubectl version --client'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
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
