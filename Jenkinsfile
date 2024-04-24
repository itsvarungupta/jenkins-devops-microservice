pipeline {
	agent any
	environment{
		dockerhome= tool 'myDocker'
		mavenhome= tool 'myMaven'
		JAVA_HOME= tool 'Java 1.8'
		PATH="$JAVA_HOME:$dockerhome/bin:$mavenhome/bin:$PATH"
	}
	stages{
		stage('Checkout') {
			steps{
				echo "JAVA_HOME -$JAVA_HOME"
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
		stage('Compile') {
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps{
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
}	
