pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        sh 'git clone "https://github.com/jarryabbas110/react-music-player.git"'
      }
    }

    stage('') {
      steps {
        sh '''cd react-music-player
npm install
npm run build'''
      }
    }

  }
}