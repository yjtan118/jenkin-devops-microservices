//DECLARATIVE
pipeline {
	agent any
	//agent { docker {image 'maven:3.6.3'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD ID - $env.BUILD_ID"
				echo "JOB NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}			
		}
		stage('Test') {
			steps {
				echo "Test"
			}			
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}			
		}
	} 
	post {
		always {
			echo "Im awesome. I run always"
		}
		success {
			echo "I run when you are successful"
		}
		failure {
			echo "I run when you fail"
		}
	}

}
