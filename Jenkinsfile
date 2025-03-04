pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    parameters {
        choice(name: 'COLLECTION_NAME', choices: ['Collection1.postman_collection.json', 'preparations.postman_collection.json', 'ThirdCollection.postman_collection.json'], description: 'Sélectionnez la collection Postman à exécuter')
    }   
    stages {
        stage('Check Newman Version') {
            steps {
                sh 'newman --version'
            }
        }
        stage('Run API Tests') {
            steps {
                // Exécution des tests API avec la collection choisie
                sh "newman run collections/${COLLECTION_NAME} -e environements/environs.postman_collection.json"
            }
        }
    }
}
