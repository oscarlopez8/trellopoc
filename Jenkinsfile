pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        image 'python:3-alpine'
      }
    }
    stage('Install Requirements') {
      steps {
        withEnv(["HOME=${env.WORKSPACE}"]) {
          sh 'pip3 install -r requirements.txt'
        }
      }
    }
    stage('API') {
      steps {
        sh 'behave trello/api/features'
      }
    }
  }
}