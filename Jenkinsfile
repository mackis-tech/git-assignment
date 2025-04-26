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
			sh 'sudo sh test.sh'
			sh 'id'
			sh 'pwd'
			}
		}
	}
}
