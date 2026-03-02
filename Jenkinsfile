pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Ilakkiya182005/jenkins-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-static-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop my-site || true'
                sh 'docker rm my-site || true'
                sh 'docker run -d -p 8081:80 --name my-site my-static-site'
            }
        }
    }
}