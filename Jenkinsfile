pipeline {
  agent any
  environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerlogin')
	}  
	stage('Build') {

			steps {
				sh 'docker build -t xplatformexpleo/demoapp_deploy:${BUILD_NUMBER} .'
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
    stage('Push') {

			steps {
				sh 'docker push xplatformexpleo/demoapp_deploy:${BUILD_NUMBER}'
			}
		}
	}
}
