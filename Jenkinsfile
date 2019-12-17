pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
  }
  stages {
   stage('build') {
	steps {
	  sh 'docker build -t mohsinejaz/project-fib-nginx .'
           }
      }
    stage('Publish') {
        steps{
            script {
                docker.withRegistry( '', registryCredential ) {
		 sh 'docker push mohsinejaz/project-fib-nginx:latest'
               } 
           }
        }       
    }
  }
}
