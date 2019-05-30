pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Praveentps/Hackthon-2019.git', branch: 'master')
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