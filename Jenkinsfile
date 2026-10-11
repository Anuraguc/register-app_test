pipeline{
  agent { label 'jenkins-agent' }
  tools{
    jdk 'java21'
    maven 'maven3'
  }
  stages{
    stage("clean up workspace"){
      steps{
        cleanWs()
      }
    }
    stage("checkout from git"){
      steps{
        git branch: 'main' , credentialsId: 'github' , url: 'https://github.com/Anuraguc/register-app_test.git'
      }
    }
    stage("build application"){
      steps{
        sh "mvn clean package"
      }
    }
    stage("Test application"){
      steps{
        sh "mvn test"
      }
    }
  }
}
