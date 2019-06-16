node{'master'}
    
properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

node('master'){  
    
    def mavenHome=tool name: "maven", type: "maven"
    
 stage('Checkout the code') {
   git branch: 'master', credentialsId: '7467f260-7644-4317-b58f-1439a397ceec', url: 'https://github.com/devops122/Maven-Web-Project1.git'  
 }
 
 stage('Build')
 {
  bat  "${mavenHome}/bin/mvn clean package"
 }
 
 
 stage('DeplotoTomcat'){
     
     bat "copy  $workspace\pipeline example\target\maven-web-project-1.0-SNAPSHOT.war  C:\Devops\apache-tomcat-7.0.94\webapps\"
 }
 
}
