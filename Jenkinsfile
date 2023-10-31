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
		stage('Build') {
			steps {
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
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
