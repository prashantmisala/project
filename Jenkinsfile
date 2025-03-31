pipeline {
    agent {label'slave'}
	
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
