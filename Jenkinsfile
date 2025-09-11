pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'docker build -t app .'
				echo 'Build Done'
			}
		}
		stage('Run') {
			steps {
				sh 'docker rm -f app_container || true'
				sh 'docker run -d -p 5000:5000 --name app_container -v $WORKSPACE/app:/app app'
				echo 'Run Done'
			}
		}
		stage('Deploy') {
			steps {
				sh 'docker start app_container'
				echo 'Deploy Done'
			}
		}
	}
}
