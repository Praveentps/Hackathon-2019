pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
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
    stage('create pkg') {
      steps {
        sh 'zip -r hackathon.zip *.*'
      }
    }
  }
  environment {
    project = 'hackathon'
  }
}