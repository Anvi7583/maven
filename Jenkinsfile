pipeline {
	agent any
	tools {
		maven 'Maven'
	}
	
	stages {
		stage('Checkout') {
			steps{
				git branch: 'master', url: 'https://github.com/Anvi7583/maven.git'
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
	        		sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar
'
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

	        
	    
