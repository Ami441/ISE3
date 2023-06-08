pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-java-app .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'docker-hub-credentials', variable: 'DOCKER_HUB_CREDENTIALS')]) {
                    sh 'echo $DOCKER_HUB_CREDENTIALS | docker login -u <Amit441> --password-stdin'
                    sh 'docker tag my-java-app <Amit441>/my-java-app'
                    sh 'docker push <Amit441>/my-java-app'
                }
            }
        }
    }
}
