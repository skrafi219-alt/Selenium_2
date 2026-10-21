pipeline{
	
	agent any
	
	stages{
		
		stage('checkout'){
			steps{
				checkout scm
			}
		}
		
		stage('Run Testng Tests'){
			steps{
				bat 'mvn clean test'
			}
		}
	}
	
	post {
        always {
            junit testResults: 'target/surefire-reports/*.xml',
                  allowEmptyResults: true
        }
    }
}