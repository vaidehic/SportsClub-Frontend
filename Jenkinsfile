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
}
}
