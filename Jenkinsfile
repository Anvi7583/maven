pipeline {
	agent any
	tools {
		maven 'Maven'
	}
	
	stages {
		stage('Checkout') {
			steps{
				git branch: 'master', url: ''
			}
		}
	        
	        stage('Build') {
	        	steps {
	        		sh 'mvn clean package'
	        	}
	        }
	        
	        stage('Test') {
	        	steps {
	        		sh 'mvn test'
	        	}
	        	
	        }
	        
	        stage('Run') {
	        	steps {
	        		sh 'java -jar target/maven-1.0-SNAPSHOT.jar'
	        	}
	        }
	    }
	    post {
	    	success{
	    		echo 'Build and deployment Successful'
	    	}
	    	failure {
	    		echo 'Build failed'
	    	}
	   }
}

	        
	    
