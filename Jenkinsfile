pipeline {
    agent any

    stages {
        stage('Clean up'){
            steps {
                sh 'chmod +x cleanup_docker.sh'
                sh './cleanup_docker.sh'
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