pipeline {
    agent any
    parameters {
	string(name:'STAGE', defaultValue: 'deploy', description: 'deploy/destroy')
    }
    stages {
        stage('state') {
            steps {
		agent {
		   docker {
		     image 'alpine\helm'
		     }
		    }
		     steps {
                      if(params.STAGE == 'deploy'){
           	      }
	   	      else if(params.STAGE == 'destroy'){
		      }
	  	      else{
		        echo 'wrong decision'
		      }
                     }
                   }
                }
            }
        }
    

