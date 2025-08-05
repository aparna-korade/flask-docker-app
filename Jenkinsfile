pipeline {
  agent { label 'docker' }

  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/aparna-korade/flask-docker-app.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t flask-app .'
      }
    }

    stage('Deploy Containers') {
      steps {
        sh 'docker-compose down || true'
        sh 'docker-compose up -d'
      }
    }
  }
}
