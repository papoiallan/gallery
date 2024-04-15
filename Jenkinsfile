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
        
    }    
}