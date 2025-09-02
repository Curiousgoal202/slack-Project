pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building..."
            }
        }
    }
    post {
        success {
            slackSend (
                channel: '#help-123',
                message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded!",
                webhookUrl: "https://hooks.slack.com/services/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"
            )
        }
        failure {
            slackSend (
                channel: '#help-123',
                message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!",
                webhookUrl: "https://hooks.slack.com/services/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"
            )
        }
    }
}
