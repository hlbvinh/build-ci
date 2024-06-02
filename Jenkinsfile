pipeline {
    agent any

    stages {
        stage('Clean up'){
            steps {
                sh 'chmod +x docker-cleanup.sh'
                sh './docker-cleanup.sh'
            }
        }
        stage('Docker login'){
            steps {
                sh 'export DOCKER_USERNAME=hlbvinh'
                sh 'export DOCKER_PASSWORD=z(CRtK/4L$w5cP+'
                sh 'echo $DOCKER_PASSWORD | docker login --username $DOCKER_USERNAME --password-stdin'
            }
        }
        stage('Build') {
            steps {
                sh 'docker --version'
                sh 'docker build -t hlbvinh/nginx:custom .'
            }
        }
        stage('Store image'){
            steps {
                sh 'docker push hlbvinh/nginx:custom'
            }
        }
    }
}