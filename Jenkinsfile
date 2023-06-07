node("JenkinsSlave"){
	stage("Code Checkout"){
		checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/JuanjoGrak/SonarQubeNodeJS.git']])
	}
	stage("Build Automation"){
		sh """
			ls -lart
			npm install
			npm run build
		"""
	}
	stage("Test Automation"){
		sh """
			npm run test
			npm run test:e2e
		"""
	}
	stage("Code Deployment"){
		
	}
}
