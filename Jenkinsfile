#!groovy

pipeline {
	agent none
  stages {
  	stage('Maven Install') {
    	agent {
      	docker {
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Sonarqube') {
    	 agent any
      steps {
      	sh '''mvn clean verify sonar:sonar   -Dsonar.projectKey=myweb   -Dsonar.projectName='myweb'   -Dsonar.host.url=http://localhost:9000   -Dsonar.token=sqp_98c311ce52acf30fe7f9d67d2b2f6850098660e9
'''
      }
    }
    
  }
}
