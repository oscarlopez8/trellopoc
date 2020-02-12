pipeline {
  agent any
  stages {
    stage('Install Requirements') {
      steps {
        image 'python:3-alpine'
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