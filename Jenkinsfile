pipeline {	
	agent any	
	tools {	    
		maven 'my-maven'		
		jdk 'my-jdk'	
	}	
	stages {        
		stage('Clone'){			
			steps {git url:'https://github.com/rohitha987/api-gateway.git', branch:'main'}			}		
		stage('Build'){			
			steps {bat "mvn clean install -DskipTests"}		
		}		
		stage('Test'){			
			steps{bat "mvn test"}		}		
		}
		stage('Deploy') {			
			steps { bat "docker build -t apig-image ."			    
			            bat "docker run -p 8060:8060 -d --name apig-container apig-image"}		
		}		
	}
}
}
