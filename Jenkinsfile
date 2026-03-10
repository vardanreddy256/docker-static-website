pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image'
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Stop Old Container') {
            steps {
                echo 'Stopping old container if exists'
                sh 'docker stop mywebsite-container || true'
                sh 'docker rm mywebsite-container || true'
            }
        }

        stage('Deploy Container') {
            steps {
                echo 'Running new container'
                sh 'docker run -d -p 8090:80 --name mywebsite-container mywebsite'
            }
        }

    }
}            
