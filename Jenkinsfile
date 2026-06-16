pipeline{
	agent any
	
	tools{
		maven 'Maven'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch:'master' , url:'https://github.com/alcoholisme/MavenApp.git'
			}
		}
		
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		
		stage('Deploy'){
			steps{
				sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
			}
		}
		
	}
	
	post{
		success{
			echo 'build and deployment successful'
		}
		
		failure{
			echo 'build failed!'
		}
	}
}
