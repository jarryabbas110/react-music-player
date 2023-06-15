pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/jarryabbas110/react-music-player', branch: 'main')
      }
    }

    stage('Log') {
      parallel {
        stage('Log') {
          steps {
            sh 'ls -al'
          }
        }

        stage('Front-end Unit Test') {
          steps {
            sh 'npm i && npm start'
          }
        }

      }
    }

  }
}