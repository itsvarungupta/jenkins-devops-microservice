pipeline {
	agent any
	environment{
		dockerhome= tool 'myDocker'
		mavenhome= tool 'myMaven'
		PATH="$dockerhome/bin:$mavenhome/bin:$PATH"
	}
	stages{
		stage('Build') {
			steps{
				echo "PATH - $PATH"
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test') {
			steps{
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps{
				echo "Integration Test"
			}
		}
	}
}	
