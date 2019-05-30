pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:6-alpine'
    }

  }
  stages {
    stage('checkout') {
      parallel {
        stage('checkout') {
          steps {
            git(url: 'https://github.com/Praveentps/Hackthon-2019.git', branch: 'master')
          }
        }
        stage('install zip') {
          steps {
            sh 'yum install zip*'
          }
        }
      }
    }
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
  }
  environment {
    project = 'hackathon'
  }
}