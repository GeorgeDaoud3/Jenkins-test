pipeline{
	agent any
	stages {
		stage('Clone repository') {
			/* Let's make sure we have the repository cloned to our workspace */

			checkout scm
		}
	  stage('maven install') {
		steps {
		  withMaven( maven: 'Maven3') {
				sh 'mvn -f ./test/ clean install'
			}
		}
	  }

	}
}