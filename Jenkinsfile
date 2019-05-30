pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'centos/nodejs-6-centos7'
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
            sh 'yum -y install zip'
          }
        }
      }
    }
    stage('install npm') {
      steps {
        sh '''yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_6.x | bash -
yum -y install nodejs'''
      }
    }
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('create pkg') {
      steps {
        sh 'zip hack.zip /var/jenkins_home/workspace/ASCENA-2019_master/*'
      }
    }
  }
  environment {
    project = 'hackathon'
  }
}