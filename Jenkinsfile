pipeline {
	agent { dockerfile true }
    	environment {
    		DOCKERHUB_CREDENTIALS = credentials('dockerHub')
    	}
    	stages {
        	stage('Test') {
            		steps {
            			echo 'Check Node Version'
                		sh 'node --version'
            		}
        	}
        	stage('Login') {
      			steps {
        			sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      			}
    		}
		stage('Push') {
      			steps {
        			sh 'docker push node-sample:latest'
      			}
    		}
	} 
}
