pipeline{
     agent any 
            stages{
                   stage('Checkout'){
                                   steps{
                                        git branch:'master', url:'https://github.com/Curiousgoal202/slack-Project.git'
                                                 }
                                            }
                                         }
            post{
                  success{
                         slacksend(  channel: '#johncena',
                message: "✅ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded! 🎉",
                color: '#36a64f'
            )                 
                        }
                 failure{
                        slackSend(
                channel: '#johncena',
                message: "❌ Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed! 🚨",
                color: '#FF0000'
            )
                         }
                     }
                 }

