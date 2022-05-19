pipeline {
    agent { docker { image 'alpine/helm' } }
    parameters {
	string(name:'STAGE', defaultValue: 'deploy', description: 'deploy/destroy')
    }
    stages {
        stage(${params.STAGE}) {
            steps {
                if(params.STAGE == 'deploy'){
		}
		elif(params.STAGE == 'destroy'){
		}
		else{
		  echo 'wrong decision'
		}
            }
        }
    }

