pipeline {
    agent any
	
    environment {
          dockerImage = ''
	  registry = 'prashant1311/pro'
    }
	
    stages {
        stage('Validate') {
            steps {
                echo 'Validating..'
	     withMaven {	    
		sh 'mvn compile'
                sh 'mvn test'
		sh 'mvn package'     
		
		echo "${env.BRANCH_NAME}"
	     }
            }
        }
        stage('Unit Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('package') {
            steps {
                echo 'packing....'
		// sh 'mvn package'
            }
	} 
	// stage('build') {
	//       steps {
	// 	      script {    
	// 	  dockerImage = docker.build registry
	//         }
 //            }
 //        } 
    }     
} 
