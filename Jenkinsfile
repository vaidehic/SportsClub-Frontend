pipeline {
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
              sh "npm install"
              sh "npm run build"
            }
   }

}
 
//    stage('Docker Build') {
//             steps {
//                 script {
//                     docker.build("docker-vaidehi/sportsclub-angular-image:${TAG}")
//                 }
//             }
//         }
// 	stage('Pushing Docker Image to Jfrog Artifactory') {
//             steps {
//                 script {
//                     docker.withRegistry('http://172.27.59.80:8082/', 'artifactory-docker') {
//                         docker.image("docker-vaidehi/sportsclub-angular-image:${TAG}").push()
//                         docker.image("docker-vaidehi/sportsclub-angular-image:${TAG}").push("latest")
//                     }
//                 }
//             }
//         }
//         stage('Deploy'){
//             steps {
//                 sh "docker stop sportsclub-final | true"
//                 sh "docker rm sportsclub-final | true"
//                 sh "docker run --network vaidehi-sports-network --name sportsclub-final -p 8082:8080 -d docker-vaidehi/sportsclub-angular-image:${TAG}"
//             }
//         }	    
  
  
}
}
