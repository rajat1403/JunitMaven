node {
	
	
	stage('Checkout') {
	              git 'https://github.com/rajat1403/JunitMaven.git'
	       }
	
	stage('SonarQube Analysis') {
	
	               	def scannerHome = tool 'SonarQube Scanner 3.2';
   			withSonarQubeEnv('My SonarQube Server') {
   			sh "${scannerHome}/bin/sonar-scanner"
			      
	              }
	       }
	
	 stage('UnitTesting') {
	     steps{
	 
	                     sh 'mvn test'
	       }
	        
	       stage('BuildCode'){
	           steps{
	        sh 'mvn clean install'
	           }
	  }
	  } 
	}

