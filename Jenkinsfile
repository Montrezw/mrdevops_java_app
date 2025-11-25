@Library('my-shared-library') _

pipeline{
    agent any
    stages{
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