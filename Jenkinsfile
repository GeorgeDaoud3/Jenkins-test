pipeline{
	agent any
	stages {
		stage('Clone repository') {
			/* Let's make sure we have the repository cloned to our workspace */
			steps {
				checkout scm
			}
		}
		stage('maven install') {
			steps {
			  withMaven( maven: 'Maven3') {
					sh 'mvn -f ./BinaryCalculatorWebapp/ clean package'
				}
			}
		}
		node{
		stage('Create Docker image') {
			steps {
				
					docker.build("CalculatorWebapp", "./BinaryCalculatorWebapp")
				}
			}
		}
		}
	}
}