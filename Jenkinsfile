pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('.'){
                script{
                    my_images = docker.build("nginx:custom")
                }
            }
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