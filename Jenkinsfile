pipeline {
  agent any

  stages {
    stage('Build Docker') {
      steps {
        sh '/opt/homebrew/bin/docker-compose build'
      }
    }

    stage('Run Docker') {
      steps {
        sh '/opt/homebrew/bin/docker-compose up -d'
      }
    }
  }
}
