#!groovy

node {
  
	   
       stage('Checkout'){

          checkout scm
       }

       stage('Compiling'){

          bat 'mvn install'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    bat 'mvn sonar:sonar'
                }
       
}
