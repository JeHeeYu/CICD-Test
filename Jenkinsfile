pipeline {
  agent any

  stages {
    stage('Build Docker') {
      steps {
        sh '/usr/local/bin/docker-compose build'
      }
    }

    stage('Run Docker') {
      steps {
        sh '/usr/local/bin/docker-compose up -d'
      }
    }
  }
}
