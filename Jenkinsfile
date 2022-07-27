pipeline {
  agent any
  tools {
    maven 'maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: 'Deployer', path: '', url: 'http://34.239.128.157:8080/')], contextPath: '/web', onFailure: false, war: '**/hello-world.war'
      }
     }
   }
 }
}

