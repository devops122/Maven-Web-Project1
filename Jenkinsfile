#!groovy

node {
  
	   
       stage('Checkout'){

          checkout scm
       }

       stage('Compiling'){

          bat 'mvn package'
       }
      stage('UploadArtifactIntoNexus') {
 
    sh "${mavenHome}/bin/mvn deploy"
}   
     
       
}
