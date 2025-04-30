pipeline {
  agent any

  stages {
    stage('Clone repo') {
      steps {
        git branch: 'main', url: 'https://github.com/AryanJain1304/plag.git'
      }
    }

    stage('Build Docker Images') {
      steps {
        sh 'docker-compose build'
      }
    }

    stage('Run Containers') {
      steps {
        sh 'docker-compose up -d'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'docker-compose exec server npm test || true'
        sh 'docker-compose exec client npm test || true'
      }
    }
  }
}
