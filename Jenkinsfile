pipeline {
    agent any
	parameters([string(name:'STAGE', choices: ['deploy','destroy'], description: 'deploy/destroy')])
    stages {
	    stage('Setup parameters') {
            steps {
                script { 
                    properties([
                        parameters([
                            choice(
                                choices: ['deploy', 'destroy'], 
                                name: 'STAGE'
                            )
                        ])
                    ])
                }
            }
        }
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
