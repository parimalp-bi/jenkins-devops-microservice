pipeline {
	agent { docker { image 'maven:3.6.3' } }
	agent any
	environment {
		dockerHome= tool 'myDocker'
		mavenHome= tool 'myMaven'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
				steps{
					sh 'mvn --version'
					sh 'docker version'
				}
		}
		// stage('Compile'){
		// 		steps{
		// 			// sh 'mvn clean compile'
		// 			//sh 'docker version'
		// 		}
		// }

		stage('Test'){
				steps{
					echo 'Test'
				}
		}		
		stage('Integration test'){
				steps{
					echo 'Integration test'
				}
		}
	}
}
