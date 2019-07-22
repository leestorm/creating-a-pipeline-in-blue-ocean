pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 80:80'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install webpack'
        sh 'npm install --save-dev mini-css-extract-plugin'
        sh 'npm install'
      }
    }
  }
}