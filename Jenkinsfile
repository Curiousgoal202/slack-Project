pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        success {
            slackSend(
                channel: '#help-123',
                message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded!",
                color: 'good'
            )
        }
        failure {
            slackSend(
                channel: '#help-123',
                message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!",
                color: 'danger'
            )
        }
    }
}
