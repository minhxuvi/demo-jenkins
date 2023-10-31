pipeline {
	agent any
	// agent {
	// 	docker {
	// 		image 'maven:3.6.3'
	// 	}
	// }
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$PATH:$dockerHome/bin:$mavenHome/bin"
	}
	stages{
		stage('Checkout') {
			steps {
				echo "Checkout"
			}
		}

		stage('Build') {
			steps {
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Intergration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}

	post{
		always{
			echo "always"
		}
		success{
			echo "success"
		}
		failure{
			echo "failure"
		}
	}

}
