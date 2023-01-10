pipeline {
    agent any

    environment {
        registryCredentials = "nexus"
        registry = "nexus:8081"
    }

    stages {

        stage('Building our image') {
            steps{
                    script {
			echo "build has started"
                        docker.build("alpine-test")
                    }
               
            }
        }
        stage('pushing image') {
            steps{
                    script {
			echo "push has started"
                        docker.withRegistry( 'http://'+registry, registryCredentials ) 
                        dockerImage.push('latest')
                    }
               
            }
        }
 

	
        }
    
}
