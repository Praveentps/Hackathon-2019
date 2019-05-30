pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'centos/nodejs-6-centos7'
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
  }
  environment {
    project = 'hackathon'
  }
}