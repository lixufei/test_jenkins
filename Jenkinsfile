node {
	stages {

		stage('Build') {

			steps {
					def msg
					def color='#D4DADF'
					try {
						msg="saul is happy"
					} catch (e) {
						msg="saul is not happy"
							currentBuild.result = 'FAILURE'
							throw e
					} finally {

						slackSend(color: color, message: msg)
							notifySlack(currentBuild.result)
					}

			}
		}
	}
}

