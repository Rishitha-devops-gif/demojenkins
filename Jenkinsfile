pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Rishitha-devops-gif/demojenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-page .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f html-container || true
                docker run -d --name html-container -p 8080:80 html-page
                '''
            }
        }
    }
}
