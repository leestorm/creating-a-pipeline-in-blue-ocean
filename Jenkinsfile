pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        docker {
          image 'node:6-alpine'
          args '-p 80:80'
        }

      }
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
  }
  environment {
    CI = 'true'
  }
}