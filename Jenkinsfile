pipeline {
    agent any
    stages {
        stage('Git checkout') {
            steps {
                sh "echo passed"
            }
        }
        stage('Deploy') {
            steps {
                sh "docker run -d -p 8082:80 dorwardv/wordpress-sqlite-nginx-docker"
            }
        }
        
    }
}
