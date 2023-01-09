pipeline {
    agent any

    environment {
        registry = "dockerq12121212/app"
        registryCredential = 'dockerhub_id'
        dockerImagetag = ''
        dockerImageLatest=''
    }

    stages {

        stage('Building our image') {
            steps{
                    script {
			echo "build has started"
                        docker.build("nginx_test")
                    }
               
            }
        }
 

	
        }
    
}
