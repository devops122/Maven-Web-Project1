#!groovy

node {
  
	   
       stage('Checkout'){

          checkout scm
       }

       stage('Compiling'){

          bat 'mvn package'
       }
      stage('UploadArtifactIntoNexus') {
 
          sh   'mvn deploy'
}   
     
       
}
