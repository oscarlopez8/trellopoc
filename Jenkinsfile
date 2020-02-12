pipeline {
  agent any
  stages {
    stage('API') {
      steps {
        sh 'behave trello/api/features'
      }
    }
  }
}