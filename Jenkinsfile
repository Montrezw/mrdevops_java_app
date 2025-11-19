@Library('my-shared-library') _

pipeline{
    agent any
    tools {
        maven 'Maven 3.8.1' // Use the name configured in Global Tool Configuration
    }
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
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

        stage('Integration'){
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }

        stage('Static code analysis; Sonarqube'){
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }
    }
}