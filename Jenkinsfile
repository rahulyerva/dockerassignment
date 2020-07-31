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
          withDockerRegistry([credentialsId: "9a35b249-0bcf-4562-bc96-bbc6054d3f52", usernameVariable: 'HUB_USER', passwordVariable: 'HUB_TOKEN', url: "https://registry.hub.docker.com/" ]){ 
          sh 'docker login -u rahulyerva -p $HUB_TOKEN
          sh 'docker push rahulyerva/nginxphp'     
          }
          
        }
     }
   }
}

