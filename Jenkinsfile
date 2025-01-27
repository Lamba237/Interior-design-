pipeline {
    agent {
        docker {
            image 'node:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t Interior-design- .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run Interior-design- ./run-tests.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run Interior-design- ./deploy.sh'  // Create this script for deployment
            }
        }
    }
}