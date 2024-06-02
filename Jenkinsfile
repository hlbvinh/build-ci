pipeline {
    agent any

    stages {
        stage('Clean up'){
            steps {
                sh 'chmod +x docker-cleanup.sh'
                sh './docker-cleanup.sh'
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