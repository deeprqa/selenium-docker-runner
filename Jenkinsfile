pipeline{
	agent any
	stages{
	    stage("Start Grid"){
	        steps{
	            sh "docker-compose up -d hub chrome firefox"
	        }
	    }
	    stage("Run Test"){
        	   steps{
                   sh "docker-compose up search-module parabank-module"
               }
        }
	    stage("Bring Grid Down"){
	        steps{
	            sh "docker-compose down"
	        }
	    }
	}
}
