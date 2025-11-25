@Library('my-shared-library') _

pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                checkout scmGit(
                    branches: [[name: 'main']], 
                    extensions: [], 
                    userRemoteConfigs: [[url: 'https://github.com/Montrezw/mrdevops_java_app.git']]
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