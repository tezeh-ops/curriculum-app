pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/tezeh-ops/curriculum-app', branch: 'dev')
      }
    }

    stage('List All Files') {
      parallel {
        stage('List All Files') {
          steps {
            sh 'ls -ls'
          }
        }

        stage('Front-End Unit-Test') {
          steps {
            sh 'cd curriculum-front && npm i && npm run test:unit'
          }
        }

      }
    }

    stage('Build') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . -t tezeh/curriculum-front'
      }
    }

  }
}