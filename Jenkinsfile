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
		sh 'env'
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
