@Library('my-shared-library') _

pipeline{
    agent any
    tools {
        maven 'Maven 3.8.7' // Use the name configured in Global Tool Configuration
    }
    stages{
        stage('Git Checkout'){
            steps{
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/Montrezw/mrdevops_java_app.git"
                )
            }
        }
        stage('Unit Test Maven'){
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage('Integration test'){
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
    }
}