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
        when { expression {
            params.action == 'create'
        }}
        stage('Git Checkout'){
            steps{
                script{
                    gitCheckout()
                }
            }
        }
        stage('Unit Test Maven'){
            when { expression {
                params.action == 'create'
            }}
            steps{
                script{
                    mvnTest()
                }
            }
        }

        stage('Integration'){
            when { expression {
                params.action == 'create'
            }}
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }

        stage('Static code analysis; Sonarqube'){
            when { expression {
                params.action == 'create'
            }}
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }
    }
}