pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
          dir('/react-music-player') {
          sh 'npm install'
          sh 'npm run build'
        }
      }
    }

    stage('Build Docker Image') {
      steps {
        withCredentials([usernamePassword(credentialsId: '99802012-7a97-4458-a8c0-9f02c94bd058', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
          script {
            docker.withRegistry('https://registry.hub.docker.com', DOCKER_USERNAME, DOCKER_PASSWORD) {
              docker.image('jarryabbas110/musicImage:latest').push()
            }
          }
        }
      }
    
    }
    
    stage('Push to Docker Hub') {
      steps {
        script {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials-id') {
            docker.image('your-docker-hub-username/image-name:tag').push()
          }
        }
      }
    }

     

  }
}
