pipeline {
    agent any
    
    environment {
        // Variables d'environnement globales
        MY_ENV_VAR = 'production'
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'whoami'
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
