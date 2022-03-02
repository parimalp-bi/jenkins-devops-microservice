pipeline {
	//agent { docker { image 'maven:3.6.3' } }
	agent any
	stages{
		stage('Build'){
				steps{
					echo 'Build'
					echo "$PATH"
					echo "$env.BUILD_NUMBER"
				}
		}
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
