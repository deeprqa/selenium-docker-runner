pipeline{
	agent any
	stages{
	    stage("Pull Latest Image"){
    	   steps{
    	        sh "docker pull deeprqa/selenium-docker"
    	    }
    	}
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
	}
	post{
	    always{
	        archiveArtifacts artifacts: 'output/**'
	        sh "docker-compose down"
	    }
	}
}
