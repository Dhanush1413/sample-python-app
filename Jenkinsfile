pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Dhanush1413/sample-python-app.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t sample-python-app:latest .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop sample-python-app || true'
                sh 'docker rm sample-python-app || true'
                sh 'docker run -d --name sample-python-app -p 5000:5000 sample-python-app:latest'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}