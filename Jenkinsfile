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
					// sh 'mvn clean compile'
					echo 'mvn clean compile'
					
				}
		}

		stage('test'){
				steps{
					echo 'mvn test'
				}
		}		
		stage('Integration test'){
				steps{
					echo 'Integration test'
				}
		}

		stage('Package'){
				steps{
					echo 'Package Created'
					// sh 'mvn package -DskipTests'
				}
		}


		stage('Build Docker Image'){

			steps{
				script{
						dockerImage = docker.build("parimalppatil/currency-exchange-devops:{$env.Build_TAG}")
				}
				// docker build -t parimalppatil/currency-exchange-devops:$env.Build_TAG
			}
		}

		stage('Push Docker Image'){

			steps{
				script{ //parimalppatil_docker this global credentials created in jenkins.
						docker.withRegistry('','parimalppatil_docker') // first entry is in '' means default docker registry .. i.e docker hub
						dockerImage.push()
						dockerImage.push('latest')
						
					}
				
			}
		}		
	}
}
