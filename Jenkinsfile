pipeline {
	//agent { docker { image 'maven' } }
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
					echo "Build_NUMBER - $env.Build_NUMBER"
					echo "Build_ID - $env.Build_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "Build_TAG - $env.Build_TAG"
					echo "PATH - $PATH"
				}
		}
		stage('Compile'){
				steps{
					echo 'Compile'
					
				}
		}

		stage('Build'){
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
