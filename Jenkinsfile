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
            steps{
                echo "I am checkout"
            }
        }
		stage("Compile"){
			steps{
                sh "mvn clean compile"
			}
		}
		stage("TEST"){
			steps{
				echo "mvn test"
			}
		}
		stage("Integration Test"){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}

        stage("Package"){
            steps{
                sh "mvn package -DskipTests"
            }
        }

    //     stage("Build Docker Image"){
    //         steps{
    //             script{
    //                 dockerImage = docker.build('shabbirhythm/currency-exchange-devops-lol:${env.BUILD_TAG}')
    //             }
    //         }
    //     }
    //     stage("Push Docker Image"){
    //         steps{
    //             script{
    //                 dockerImage.withRegistry("", "dockerhub");
    //                 dockerImage.push();
    //                 dockerImage.push('latest');
    //             } 
    //         }
    //     }
	// }
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
