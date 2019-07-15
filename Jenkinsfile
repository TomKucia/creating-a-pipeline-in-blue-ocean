pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm install'
          }
        }
        stage('Clean') {
          environment {
            CI = 'true'
          }
          steps {
            sh 'ls -l'
          }
        }
        stage('Test') {
          steps {
            sh './jenkins/scripts/test.sh'
          }
        }
      }
    }
  }
}