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
                dir("app") {
                    script {
			echo "build has started"
                        dockerImagetag = docker.build registry + ":$BUILD_NUMBER"
                        dockerImageLatest = docker.build registry + ":latest"
                    }
                }
            }
        }
 
        stage('Deploy to dockerhub') {
            steps{
                script {
                   	docker.withRegistry( '', registryCredential ) {
                        dockerImagetag.push()
                        dockerImageLatest.push()
                    }
                }
            }
        }
	
        }
    
}
