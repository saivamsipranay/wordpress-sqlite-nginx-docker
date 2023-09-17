pipeline {
    agent any
    stages {
        stage('Git checkout') {
            steps {
                sh "echo passed"
            }
        }
        stage('Docker Image Build') {
            environment {
                DOCKER_IMAGE = "saivamsipranay/exactspace:${BUILD_NUMBER}"
            }
            steps {
                sh "docker image build -t ${DOCKER_IMAGE} ."   
            }
        }
        stage('Deploy') {
            environment {
                DOCKER_IMAGE = "saivamsipranay/exactspace:${BUILD_NUMBER}"
            }
            steps {
                sh "docker run -d -p 80:80 ${DOCKER_IMAGE}"
            }
        }
        
    }
}