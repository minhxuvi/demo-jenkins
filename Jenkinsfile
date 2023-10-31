pipeline {
	agent any
	stages{
		stage('Build') {
			steps {
				echo "Build"
			}
		}
	}
	stages{
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
