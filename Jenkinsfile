pipeline { 
    environment { 
        registry = "rahulyerva/nginxphp" 
        registryCredential = 'e4e457f1-ed5e-4a39-8cf1-b5670da8f5b2' 
        dockerImage = 'nginxphp' 
    }
    agent any 
    stages { 
        stage('Cloning our Git') { 
            steps { 
                git 'https://github.com/rahulyerva/dockerassignment.git' 
            }
        } 
        stage('Building our image') { 
            steps { 
                script { 
                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 
                }
            } 
        }
    }
}
