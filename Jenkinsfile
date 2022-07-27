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
       deploy adapters: [tomcat9(credentialsId: '53d5f100-d240-4c47-a43c-c0ada4780738', path: '', url: 'http://34.239.128.157:8080/')], contextPath: 'myapp', war: '**/hello-world.war'
      }
     }
   }
 }
}

