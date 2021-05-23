pipeline {
    agent any
    environment {	
          dockerimage =''
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
	stages('build'){
		steps{
		   dockerimage = docker.build registry 	
            }
        } 
    }     
}
