pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'hello world'
                sh 'hahaha'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'LiangLingrui is happy!'
            slackSend channel: '#test-slack',
                  color: 'good',
<<<<<<< 717eeece958516f26740fd32857d309e613d1ed6
                  message: "Lisa Huang is happy!"
            sh 'curl -F file=@siwo-thoughtworks.png -F channels=#test-slack -F token=xoxp-351277970144-360652542944-367054471605-fa0e8e39ba0600a74c4d91544f5f7ccb https://slack.com/api/files.upload'
        }
        failure {
             echo 'LiangLingrui is not happy.'
            slackSend channel: '#test-slack',
                  color: 'danger',
                  message: "Lisa Huang is not happy!"
=======
                  message: "xuya is happy."
            sh 'curl -F file=@siwo-thoughtworks.png -F channels=#test-slack -F token=xoxp-351277970144-360652542944-367054471605-fa0e8e39ba0600a74c4d91544f5f7ccb https://slack.com/api/files.upload'
        }
        failure {
            echo 'This will run only if failed'
			slackSend channel: '#test-slack',
                  color: 'danger',
                  message: "xuya is not happy."
>>>>>>> xuya's modifying
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
