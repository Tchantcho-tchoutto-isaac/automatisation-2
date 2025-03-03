pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    stages {
        stage('Install Newman Reporter htmlextra') {
            steps {
                // Installation du reporter avec --unsafe-perm pour contourner les problèmes de permissions
                sh 'npm install -g newman-reporter-htmlextra --unsafe-perm'
            }
        }
        stage('Check Newman Version') {
            steps {
                sh 'newman --version'
            }
        }
        stage('Run API Tests collection1') {
            steps {
                // Exécution des tests API avec le reporter htmlextra
                sh 'newman run collections/Collection1.postman_collection.json '
            }
        }
        stage('Run API Tests collection2') {
            steps {
                // Exécution des tests API avec le reporter htmlextra
                sh 'newman run collections/commentaire.postman_collection.json'
            }
        }
    }
}
