pipeline {
   environment {
    registry = "rahulyerva/nginxphp"
    registryCredential = 'rahulyerva'
    dockerimage = 'nginxphp:latest'
  }
   agent any
   stages {
     stage('pull repo'){
    	steps {
          git 'https://github.com/rahulyerva/dockerassignment.git'
        }
     }
     stage('Build Docker Images from dockerfile'){
        steps {
         script {
         dockerImage = docker.build registry + ":$BUILD_NUMBER"
          }
        }
      }
     stage('Push docker image to Dockerhub'){
        steps {
          script {
          docker.withRegistry( 'https://registry.hub.docker.com', dockerhub ) {
          dockerImage.push()
               }
             }
        }
     }
   }
}

