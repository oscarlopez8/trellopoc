pipeline {
  stages {
    stage('build') {
      steps {
        sh 'python --version'
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