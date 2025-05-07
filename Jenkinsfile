pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build("flask-app:${env.BUILD_ID}")
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    docker.image("flask-app:${env.BUILD_ID}").run("-p 5000:5000")
                }
            }
        }
    }
}
