pipeline {
    agent any
    
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Nom de la branche à construire')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Exécuter les tests')
        choice(name: 'DEPLOY_ENV', choices: ['dev', 'staging', 'prod'], description: 'Choisissez l’environnement de déploiement')
    }
    
    environment {
        KUBECONFIG = /tmp/kubeconfig.yml
        KUBECONFIG_FILE = credentials('k8s-credentials') // Use your Kubernetes credentials ID
    }

    stages {
        stage('Installing kubectl') {
            steps {
                sh 'curl -LO https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl'
                sh 'chmod +x ./kubectl'
                sh './kubectl version'
            }
        }
        stage('Setup KUBECONFIG') {
            steps {
                sh 'env'
                sh 'cat ${KUBECONFIG_FILE} > ${KUBECONFIG}'
                sh './kubectl --kubeconfig /tmp/kubeconfig.yml get nodes'
            }
        }
        
    }
}
