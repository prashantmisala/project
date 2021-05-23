pipeline {
    agent any
	 dockerfile {
            filename 'Dockerfile'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    environment {	
          dockerImage = ''
	  registry = 'prashant1311/pro'
    }
	
    stages {
        stage('Validate') {
            steps {
                echo 'Validating..'
		sh 'mvn compile'
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                echo 'packing....'
		sh 'mvn package'
            }
	} 
	stage('build') {
	      steps {
		      script {    
		  dockerImage = docker.build registry
	        }
            }
        } 
    }     
}
