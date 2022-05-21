pipeline {
    agent any
	environment {
		JENKINS_HOME="/home/azureuser"
	}
    stages {
	    stage('Setup parameters') {
            steps {
		    su azureuser
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
                        sh 'helm upgrade --install test-chart . -n kristina'
           	      }
	   	      else if(params.STAGE == 'destroy'){
			sh 'helm uninstall test-chart -n kristina'
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
