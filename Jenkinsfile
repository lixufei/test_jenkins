pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'hello world'
                sh 'npm -v'
                sh 'node -v'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
            slackSend channel: '#test-slack',
                  color: 'good',
                  message: "The pipeline completed successfully."
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
