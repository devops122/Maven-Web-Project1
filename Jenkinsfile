#!groovy

node {
  
	   
       stage('Checkout'){

          checkout scm
       }

       stage('Compiling'){

          bat 'mvn deploy'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    bat 'mvn sonar:sonar'
                }
       
}
