pipeline {
  
  environment {
        DATE = new Date().format('yy.M')
        TAG = "${DATE}.${BUILD_NUMBER}"
	//TAG = "${BUILD_NUMBER}"
    }
	
   agent 
  {
	node{
		label 'linux-slave'
	}
	}

stages {
  stage("Build Project")
  {
    steps{
      script {
              sh 'npm install'
              sh 'npm run build'
            }
   }

}
 
   stage('Docker Build') {
            steps {
                script {
                    docker.build("docker-vaidehi/sportsclub-angular-image:${TAG}")
                }
            }
        }
 
	stage('Pushing Docker Image to Jfrog Artifactory') {
            steps {
                script {
                    docker.withRegistry('http://172.27.59.80:8082/', 'artifactory-docker') {
                        docker.image("docker-vaidehi/sportsclub-angular-image:${TAG}").push()
                        docker.image("docker-vaidehi/sportsclub-angular-image:${TAG}").push("latest")
                    }
                }
            }
        }
//    stage('Docker Run') {
//     steps{
//       sh "docker run -d -p 8090:8080 docker-vaidehi/sportsclub-angular-image:${TAG}"
//     }
//   }
  
    stage('Deploy'){
            steps {
                sh "docker stop sportsclub-angular-image | true"
                sh "docker rm sportsclub-angular-image | true"
<<<<<<< HEAD
                sh "docker run --network vaidehi-sports-network --name sportsclub-angular-image -p 8082:80 -d docker-vaidehi/sportsclub-angular-image:${TAG}"
=======
                sh "docker run --network vaidehi-sports-network --name sportsclub-angular-image -p 8092:8080 -d docker-vaidehi/sportsclub-angular-image:${TAG}"
>>>>>>> 180a5cc411c6ff360611a11c8bed824b83e9d10e
            }
        }
//         stage('Deploy'){
//             steps {
//                 sh "docker stop sportsclub-final | true"
//                 sh "docker rm sportsclub-final | true"
//                 sh "docker run --network vaidehi-sports-network --name sportsclub-final -p 8087:80 -d docker-vaidehi/sportsclub-angular-image:${TAG}"
//             }
//         }	    
  
  
}
}
