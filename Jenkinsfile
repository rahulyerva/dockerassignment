pipeline {
   agent any
   tools {
     docker '1.13.1'
   }
   stages {
     stage('pull repo'){
    	steps {
          git 'https://github.com/rahulyerva/dockerassignment.git'
        }
     }
     stage('Build Docker Images from dockerfile'){
        steps {
          sh 'docker build -t nginxphp:latest .'
        }
     stage('Push docker image to Dockerhub and ECR'){
        steps {
          withDockerRegistry([ credentialsId: "e4e457f1-ed5e-4a39-8cf1-b5670da8f5b2", url: "https://hub.docker.com/repository/docker/rahulyerva/nginxphp:" ]) {
            sh 'docker push rahulyerva/nginxphp:latest' 
          }
          
        }
     }
   }
}
 
