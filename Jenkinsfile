pipeline {
  agent any

  stages {
    stage('Build Docker') {
      steps {
        sh '/usr/local/bin/docker-compose build'
      }
    }

    stage('Stop & Run Docker') {
      steps {
        sh '''
          /usr/local/bin/docker-compose down || true
          /usr/local/bin/docker-compose up -d
        '''
      }
    }
  }
}
