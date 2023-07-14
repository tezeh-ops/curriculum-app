pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/tezeh-ops/curriculum-app', branch: 'dev')
      }
    }

    stage('List All Files') {
      steps {
        sh 'ls -ls'
      }
    }

  }
}