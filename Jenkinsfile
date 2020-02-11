pipeline {
  agent any
  stages {
    stage('Install Requirements') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }
    stage('API') {
      steps {
        sh 'behave trello/api/features'
      }
    }
  }
}