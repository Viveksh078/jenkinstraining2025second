pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Viveksh078/jenkinstraining2025first.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t simplepage-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f simplepage-container || true'
                sh 'docker run -d -p 8000:80 --name simplepage-container simplepage-app'
            }
        }
    }
}
