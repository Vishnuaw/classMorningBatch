pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        git(url: 'https://github.com/msharma1/classMorningBatch', branch: 'master')
      }
    }

    stage('yumOperation') {
      parallel {
        stage('yumOperation') {
          steps {
            sh '''sudo yum update -y
sudo yum install git'''
          }
        }

        stage('createUser') {
          steps {
            sh 'sudo useradd abc'
          }
        }

      }
    }

    stage('build') {
      steps {
        build 'morningMavenPipeline'
      }
    }

  }
}