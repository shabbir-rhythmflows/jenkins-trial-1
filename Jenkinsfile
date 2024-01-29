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
	// agent any
	agent{
		docker{ image{ 'maven:3.6.3' } }
	}
	stages{
		stage("BUILD"){
			steps{
				sh 'mvn --version'
				echo "BUILD lol"
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
