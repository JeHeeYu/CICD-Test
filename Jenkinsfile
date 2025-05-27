pipeline {
  agent any

  tools {
    nodejs "Node 20"
  }

  stages {
    stage('Build Docker') {
      steps {
        sh 'docker-compose build'
      }
    }

    stage('Test & Run Check') {
      steps {
        dir('./') {
          sh 'npm install'
          sh 'npm test'
          sh 'node index.js'
        }
      }
    }

    stage('Deploy') {
      steps {
        sh '''
          docker-compose down || true
          docker-compose up -d
        '''
      }
    }
  }
}
