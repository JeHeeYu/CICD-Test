pipeline {
  agent any

  stages {
    stage('Build Docker') {
      steps {
        sh '/usr/local/bin/docker-compose build'
      }
    }

    stage('Test') {
      steps {
        dir('/Users/yjh/.jenkins/workspace/cicd-local-test') {
          sh 'npm install'
          sh 'npm test'
        }
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
