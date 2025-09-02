pipeline{
     agent any 
            stages{
                   stage('Checkout'){
                                   steps{
                                        git branch:'master', url:'https://github.com/Curiousgoal202/slack-Project.git'
                                                 }
                                            }
                                         }
post {
    success {
        slackSend(
            webhookUrl: credentials('nw'),
            message: "✅ Job ${env.JOB_NAME} #${env.BUILD_NUMBER} succeeded!",
            color: 'good'
        )
    }
    failure {
        slackSend(
            webhookUrl: credentials('nw'),
            message: "❌ Job ${env.JOB_NAME} #${env.BUILD_NUMBER} failed!",
            color: 'danger'
        )
    }
}

