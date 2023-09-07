pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
            	echo 'Check Node Version'
                sh 'node --version'
            }
        }
    }
}
