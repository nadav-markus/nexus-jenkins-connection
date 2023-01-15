pipeline {
    agent any

    environment {
        registryCredentials = "nexus"
        registry = "nexus:8081"
	NEXUS_CREDS = credentials('nexus')
    }

    stages {
        stage('Sonarqube Analysis') {
            steps{
                    script {
			 //withSonarQubeEnv(installationName: 'sonarqube'){
			    	 echo ("scan has started")
				 def scannerHome = tool 'SonarScanner 2.15';
              			 withSonarQubeEnv('sonarqube') {
      				 sh "${scannerHome}/bin/sonar-scanner"
                                 
			    }

                    
		    }
            }
        }
        stage('Building our image') {
            steps{
                    script {
			echo "build has started"
                        docker.build("alpine-test")

                    }
               
            }
        }



//         stage('pushing image') {
//             steps{
//                     script {
			  
// 			echo "push has started"
// 			sh 'docker login -u admin -p 123456 localhost:9001'
// 			sh 'docker tag alpine-test localhost:9001/alpine-test'
// 			sh 'docker push localhost:9001/alpine-test'

//                         //docker.withRegistry( 'http://'+registry, registryCredentials ) 
//                         //dockerImage.push('alpine-test')
//                     }
               
//             }
//         }
 

	
        }
    
}
