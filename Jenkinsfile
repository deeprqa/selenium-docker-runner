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
                   sh "docker-compose up search-module-chrome search-module-firefox parabank-module-chrome parabank-module-firefox"
               }
        }
	    stage("Bring Grid Down"){
	        steps{
	            sh "docker-compose down"
	        }
	    }
	}
}
