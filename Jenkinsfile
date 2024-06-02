pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker --version'
                sh 'docker build -t nginx:custom .'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}