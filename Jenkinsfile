pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t n01479079/nginx-webserver:latest .'
            }
        }
        stage('Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'n01479079', passwordVariable: 'N3-geocupuku', usernameVariable: 'n01479079')]) {
                    sh 'echo $DOCKER_HUB_PASSWORD | docker login -u $DOCKER_HUB_USERNAME --password-stdin'
                }
                sh 'docker push n01479079/nginx-webserver:latest'
            }
        }
    }
}
