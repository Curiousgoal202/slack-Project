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
        slackSend(channel: '#help-123', message: "✅ Job ${env.JOB_NAME} [${env.BUILD_NUMBER}] succeeded!")
    }
    failure {
        slackSend(channel: '#help-123', message: "❌ Job ${env.JOB_NAME} [${env.BUILD_NUMBER}] failed!")
    }
}

}
