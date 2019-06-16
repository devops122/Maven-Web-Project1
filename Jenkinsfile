node{'master'}
    
properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

node('master'){  
    
    def mavenHome=tool name: "mavenv3.6.1", type: "maven"
    
 stage('Checkout the code') {
   git branch: 'master', credentialsId: '7467f260-7644-4317-b58f-1439a397ceec', url: 'https://github.com/devops122/Maven-Web-Project1.git'  
 }
 
 stage('Build')
 {
  sh  "${mavenHome}/bin/mvn clean package"
 }
 
 stage('SonarQube Report')
 {
  sh  "${mavenHome}/bin/mvn sonar:sonar"
 }
   
  
  stage('Upload Artifacts into Nexus')
 {
  sh  "${mavenHome}/bin/mvn deploy"
 }
 
 stage('DeplotoTomcat'){
     
     sh "cp $WORKSPACE/target/*.war /opt/apache-tomcat-9.0.16/webapps/"
 }
 
}
