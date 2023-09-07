pipeline {
	agent { dockerfile true }
    	stages {
        	stage('Test') {
            		steps {
            			echo 'Check Node Version'
                		sh 'node --version'
            		}
        	}
        	stage('Docker Push') {
    	agent any
      steps {
      	withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
        	sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push node-sample:latest'
        }
      }
    }
	} 
}
