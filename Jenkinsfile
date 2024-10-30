pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "votre-utilisateur/votre-image"  // Remplacez par votre utilisateur et image Docker
        DOCKER_TAG = "latest"  // Vous pouvez utiliser la version Git avec `env.BUILD_ID` ou `env.GIT_COMMIT`
        REGISTRY_CREDENTIALS = 'docker-hub-credentials'  // ID des credentials Jenkins pour Docker Hub
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Construire l'image Docker avec un tag
                    //sh "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    // Connexion au registre Docker et push de l'image
                    //docker.withRegistry('', 'docker-hub-credentials') {
                       // sh "docker push ${DOCKER_IMAGE}:${DOCKER_TAG}"
                    }
                }
            }
        }

        stage('Deploy Docker Container') {
            steps {
                script {
                    // Arrêter et supprimer tout conteneur en cours d'exécution avec le même nom
                    //sh "docker rm -f mon-container || true"

                    // Déployer le conteneur avec la nouvelle image
                    //sh "docker run -d --name mon-container -p 80:80 ${DOCKER_IMAGE}:${DOCKER_TAG}"
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminé.'
        }
    }
}

