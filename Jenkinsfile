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
            withDockerRegistry([credentialsId: "e4e457f1-ed5e-4a39-8cf1-b5670da8f5b2", url: "https://registry.hub.docker.com/" ]) {
              sh 'docker push rahulyerva/nginxphp:latest'     
          }
        }
     }
   }
}

