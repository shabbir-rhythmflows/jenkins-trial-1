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
        stage("Checkout"){
            steps{}
        }
		stage("Compile"){
			steps{
                sh "mvn clean compile"
			}
		}
		stage("TEST"){
			steps{
				sh "mvn test"
			}
		}
		stage("Integration Test"){
			steps{
				echo "mvn failsafe:integration-test failsafe:verify"
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
