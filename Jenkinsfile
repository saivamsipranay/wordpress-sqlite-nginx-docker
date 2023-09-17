pipeline {
    agent any
    stages {
        environment {
            DOCKER_IMAGE = "saivamsipranay/ExactSpace:${BUILD_NUMBER}"
        }
        stage('Git checkout') {
            steps {
                sh "echo passed"
            }
        }
        stage('Docker Image Build') {
            steps {
                sh "docker image build -t ${DOCKER_IMAGE}"   
            }
        }
        stage('Deploy') {
            steps {
                sh "docker run -d -p 80:80 ${DOCKER_IMAGE}"
            }
        }
        
    }
}