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
                webhookUrl: credentials('nw'), 
                message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded!",
                color: 'good'
            )
        }
        failure {
            slackSend(
                webhookUrl: credentials('nw'), 
                message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed!",
                color: 'danger'
            )
        }
    }
}
