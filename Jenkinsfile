pipeline {
	 agent any
	//agent { docker {image 'maven:3.6.3'} }
	//agent { docker {image 'node:13.8'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin$PATH"
	}

	stages {
		stage('Build') {
			steps {
				sh "mvn --version"
				sh "docker version"
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
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
				echo 'Im awesome. I run always'
			}
			success {
				echo 'I run when you are success'
			}
			failure {
				echo 'I run when you are failure'
			}
	}
	
}
