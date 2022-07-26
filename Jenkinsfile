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
        deploy adapters: [tomcat9(credentialsId: 'Deployer', path: '', url: 'http://18.118.134.191:8080/')], contextPath: '/web', war: '**/hello-world.war'
      }
     }
   }
 }
}

