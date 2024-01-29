// SCRIPTED
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }

// DECLARATIVE
pipeline {
	agent any
	// agent{
	// 	docker{ image 'maven:3.6.3'  }
	// }
	environment{
		dockerHome = tool 'shabbirDocker'
		mavenHome = tool 'shabbirMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage("BUILD"){
			steps{
				sh 'mvn --version'
				sh 'docker --version'
				echo "BUILD lol"
				echo "path right now is: $PATH"
				echo "Build number now is: $env.BUILD_NUMBER"
				echo "Job name now is: $env.JOB_NAME"
				echo "Build iD now is: $env.BUILD_ID"
				echo "Build Tag now is: $env.BUILD_TAG"
				echo "Build URL now is: $env.BUILD_URL"
			}
		}
		stage("TEST"){
			steps{
				echo "TEST lol"
			}
		}
		stage("Integration Test"){
			steps{
				echo "Integration Test lol"
			}
		}
	}
	post{
		always {
			echo "I run always & I am awesome"
		}
		success {
			echo "I run when you are successful"
		}
		failure {
			echo "I run when you fail"
		}
		changed {
			echo "Status of build changed! Failure to success or success to failure"
		}
	}
}
