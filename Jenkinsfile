pipeline {
    agent any
    tools {
        nodejs 'node'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage ('Test') {
            steps {
                sh 'npm test'
            }
            post {
                failure {
                    script {
                        def buildId = env.BUILD_ID
                        mail to: 'papoi.allan@gmail.com',
                            subject: "Test Failed in Jenkins Pipeline (Build ID: ${buildId})",
                            body: "One or more tests failed in the Jenkins Pipeline (Build ID: ${buildId}). Please check the console output for details."
                    }
                }
            }
        }
        stage ('Deploy') {
            steps {
                sh 'npm run'
            }
            post {
                success {
                    script {
                        def slackMessage = "Deployment successful! Build ID: ${env.BUILD_ID}\n"
                        "Here is the link: https://gallery-9gk7.onrender.com/"
                        slackSend channel: '#general', color: 'good', message: slackMessage, teamDomain: 'Allan_IP1', tokenCredentialId: 'slack'
                    }
                    }
                }
            }
        }    
}