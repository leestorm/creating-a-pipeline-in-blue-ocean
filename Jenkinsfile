pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 8001:8001'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install --save-dev mini-css-extract-plugin'
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        input 'inished using the web site? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
      }
    }
  }
}