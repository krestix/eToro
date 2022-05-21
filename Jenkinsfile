pipeline {
    agent any
    parameters {
	string(name:'STAGE', choices: ['deploy','destroy'], description: 'deploy/destroy')
    }
    stages {
        stage('state') {
		agent {
		   docker {
		     image 'alpine/helm'
		     reuseNode true
		     }
		    }
		     steps {
                      if(params.STAGE == 'deploy'){
                        sh 'helm install test-chart . -n kristina
           	      }
	   	      else if(params.STAGE == 'destroy'){
			sh 'helm uninstall test-chart -n kristina
		      }
	  	      else{
		        echo 'wrong decision'
		      }
		     }
	}
    }
}
             
