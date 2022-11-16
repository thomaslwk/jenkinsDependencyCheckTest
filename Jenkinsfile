pipeline {
	agent any
	stages {
		// stage('Checkout SCM') {
		// 	steps {
		// 		git '/home/documents/github/jenkinsDependencyCheckTest'
		// 	}
		// }

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML --suppression suppression.xml', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}