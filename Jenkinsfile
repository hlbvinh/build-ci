pipeline {
    agent any

    environment {
        DOCKER_USERNAME = 'hlbvinh'
        DOCKER_PASSWORD = 'Vinh240198~~'
    }

    stages {
        stage('Clean up'){
            steps {
                sh 'chmod +x docker-cleanup.sh'
                sh './docker-cleanup.sh'
            }
        }
        stage('Docker login'){
            steps {
                script {
                    // Ensure the password is securely handled
                    withEnv(["DOCKER_PASSWORD=${DOCKER_PASSWORD}"]) {
                        sh 'echo $DOCKER_PASSWORD | docker login --username $DOCKER_USERNAME --password-stdin'
                    }
                }
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