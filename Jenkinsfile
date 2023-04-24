pipeline {
agent any
stages {
  stage("Build Project")
  {
    steps{
      script {
              bat "npm install"
              bat "npm run build"
            }
   }

}
}
}
