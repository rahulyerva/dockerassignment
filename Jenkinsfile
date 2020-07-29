pipeline {
   environment {
    registry = "rahulyerva/nginxphp"
    registryCredential = 'dockerhub'
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
          sh 'docker build -t nginxphp:latest .'
        }
      }
     stage('Push docker image to Dockerhub and ECR'){
        steps {
          
            sh 'docker push rahulyerva/nginxphp:latest' 
        
        }
     }
   }
}

