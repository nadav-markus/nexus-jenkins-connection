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
                        docker.build("alpine-test")
                    }
               
            }
        }
        stage('pushing image') {
            steps{
                    script {
			echo "push has started"
                        sh 'docker push http://localhost:8081/repository/myrepo/alpine-test}'
                    }
               
            }
        }
 

	
        }
    
}
