pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    stages {
       
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
                sh 'newman run collections/commentaire.postman_collection.json -e environments/environs.postman_collecti'
            }
        }
    }
}
