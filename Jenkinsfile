pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        docker {
          image 'python:3-alpine'
        }
      }
    }
    stage('Install Requirements') {
      steps {
        withEnv(["HOME=${env.WORKSPACE}"]) {
          sh 'pip install -r requirements.txt'
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