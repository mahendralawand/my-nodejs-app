pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/mahendralawand/my-nodejs-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mynodeapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop nodeapp || true'
                sh 'docker rm nodeapp || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name nodeapp mynodeapp'
            }
        }
    }
}
