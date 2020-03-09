node {
	def app

	stage('clone repository') {
		checkout scm
	}
	
	stage('build image') {
		app = docker.build('SchubertSebastian/example-app')
	}

	stage('Push image') {
		
		docker.withRegistry('https://registry.hub.docker.com','docker-hub-credentials') {
			app.push('latest')
		}
	}
}
