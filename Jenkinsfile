pipeline {
    agent any
	environment {
		JENKINS_HOME="/home/azureuser"
	}
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
