pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    parameters {
        choice(name: 'COLLECTION_NAME', choices: ['Collection1.postman_collection.json', 'preparations.postman_collection.json', 'ThirdCollection.postman_collection'], description: 'Sélectionnez la collection Postman à exécuter')
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
                sh 'newman run collections/${COLLECTION_NAME} '
            }
        }
        stage('Run API Tests collection2') {
            steps {
                // Exécution des tests API avec le reporter htmlextra
                sh 'newman run collections/${COLLECTION_NAME}   -e environements/environs.postman_collecti'
            }
        }
    }
}
