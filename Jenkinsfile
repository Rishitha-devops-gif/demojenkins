pipeline {
  agent any
  stages ('clone repo') {
    steps {
      git 'https://github.com/Rishitha-devops-gif/demojenkins.git'
    } 
  }
  stage('Build docker image') {
    steps {
      sh 'docker build -t html-page .'
    }
  }
  stage('run container') {
    steps {
      sh 'docker run -d --name html-container -p 8080:80 html-page'
    }
  }
}
