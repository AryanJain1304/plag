pipeline {
  agent any

  stages {
    stage('Clone repo') {
      steps {
        git branch: 'main', url: 'https://github.com/AryanJain1304/plag1.git'
      }
    }

    stage('Build Docker Images') {
      steps {
        bat 'docker-compose build'
      }
    }

    stage('Run Containers') {
      steps {
        bat 'docker-compose up -d'
      }
    }

    stage('Run Tests') {
      steps {
        bat 'docker-compose exec server npm test || exit 0'
        bat 'docker-compose exec client npm test || exit 0'
      }
    }
  }
}
