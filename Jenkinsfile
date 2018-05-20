pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'hello world'
                sh 'npm hahah'
                sh 'node hahah'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Lisa Huang is happy'
            slackSend channel: '#test-slack',
                  color: 'good',
                  message: "Lisa Huang is happy!"
            sh 'curl -F file=@siwo-thoughtworks.png -F channels=#test-slack -F token=xoxp-351277970144-360652542944-367054471605-fa0e8e39ba0600a74c4d91544f5f7ccb https://slack.com/api/files.upload'
        }
        failure {
            echo 'Lisa Huang is not happy'
            slackSend channel: '#test-slack',
                  color: 'danger',
                  message: "Lisa Huang is not happy"
            sh 'curl -F file=@siwo-thoughtworks.png -F channels=#test-slack -F token=xoxp-351277970144-360652542944-367054471605-fa0e8e39ba0600a74c4d91544f5f7ccb https://slack.com/api/files.upload'
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
