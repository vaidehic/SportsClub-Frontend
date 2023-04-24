pipeline {
agent any
stages {
  stage("Build Project")
  {
    step{
      script {
              bat "npm install"
              bat "npm run build"
            }
   }

}
}
}
