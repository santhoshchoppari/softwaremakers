pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  stages {
      stage("CODE FROM GIT"){
          steps{
            git branch: 'main', url: 'https://github.com/BHUPESHGCTECH/softwaremakers.git'
          
          }
      }
      stage("build code"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy stage"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'tomcatcrede', path: '', url: 'http://13.48.57.11:8080/')], contextPath: 'KTR', war: '**/*.war'
          }
      }
  }
}
