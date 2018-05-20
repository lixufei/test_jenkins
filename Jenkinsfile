pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'hello world'
                sh 'nvm list'
                sh 'node -v'
                sh 'abc'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'LiangLingrui is happy!'
			echo 'xuya is happy!'
            echo 'LiuNian is happy!'
            echo 'ChenXin is happy!'
             echo 'ZengZhipeng is happy!'
            slackSend channel: '#test-slack',
                  color: 'good',
                  message: "'LiuNian is happy!wangjie is happy."
				  message: "xuya is happy."
                  message: "'LiuNian is happy!wangjie is happy.\n ZhouXiang/LiangLingRui/ChenXin is happy"
                  message: "'LiuNian is happy!wangjie is happy.\n ZhouXiang/LiangLingRui/ChenXin is happy.\n YangKaiGuang is happy"
                  message: "'LiuNian is happy!wangjie is happy.\n ZhouXiang/LiangLingRui/ChenXin is happy.\n YangKaiGuang is happy.\n ZengZhipeng is happy"
            sh 'curl -F file=@siwo-thoughtworks.png -F channels=#test-slack -F token=xoxp-351277970144-360652542944-367054471605-fa0e8e39ba0600a74c4d91544f5f7ccb https://slack.com/api/files.upload'
        }
        failure {
             echo 'LiangLingrui is not happy.'
            echo 'wangjie is not happy'
			 echo 'xuya is not happy.'
			 echo 'Zengzhipeng is not happy.'
            slackSend channel: '#test-slack',
                  color: 'danger',
                message: "LiuNian is not happy!wangjie is not happy!"
                message: "xuya is not happy."
                message: "LiuNian is not happy!wangjie is not happy!\n ZhouXiang/LiangLingRui/ChenXin is not happy"
                 message: "Zengzhipeng is not happy."
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
