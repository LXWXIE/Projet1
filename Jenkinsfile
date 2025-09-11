pipeline {
	agent any
	stages {
		stage('Build') {
			sh 'docker build -t app .'
			echo 'Build Done'
		}
		stage('Run') {
			steps {
				sh 'docker run -d -it -p 5000:5000 --name=app_container -v app'
				echo 'Run Done'
			}
		}
		stage('Deploy') {
			steps {
				echo 'Deploy'
			}
		}
	}
}
