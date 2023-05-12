pipeline {
agent any
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
