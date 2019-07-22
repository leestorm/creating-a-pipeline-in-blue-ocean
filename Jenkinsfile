pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        sh 'npm install webpack'
        sh 'npm install --save-dev mini-css-extract-plugin'
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
  }
  environment {
    CI = 'true'
  }
}