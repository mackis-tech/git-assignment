pipeline {
	agent any
	triggers {
        	githubPush()
    	}
	
	environment {
		EMAIL_TO="mackis.tech@gmail.com"
	}
	

	stages {
		stage('checkout Code') {
			steps {
			checkout scm
			}
			}
		stage('run shell script') {
			steps {
			sh 'chmod +x test.sh'
			sh 'echo "I am here"'
			sh 'sudo sh test.sh'
			sh 'id'
			sh 'pwd'
			}
		}
	}
	post {
		failure {
			emailext (
				to: "${EMAIL_TO}",
				subject: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
				body: "Please check the log at Jenkins"
				)
			}
		}
		success {
			emailext (
				to: "${EMAIL_TO}",
				subject: "Build Succeeded: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
				body: "Please check the log at Jenkins"
				)
			}
		}
}
		
			
}
