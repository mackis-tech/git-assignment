pipeline {
	agent any

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
			sh 'test.sh'
				
			sh 'pwd'
			}
		}
	}
}
