pipeline {
    agent any
	parameters([string(name:'STAGE', choices: ['deploy','destroy'], description: 'deploy/destroy')])
    stages {
        stage('state') {
		agent {
		   docker {
		     image 'alpine/helm'
		     reuseNode true
		     }
		    }
		steps{
		script{
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

}
