@Library('my-shared-library') _

pipeline{
    agent any
    tools {
        maven 'Maven 3.8.1' // Use the name configured in Global Tool Configuration
    }
    stages{
        stage('Git Checkout'){
            steps{
                gitCheckout()
            }
        }
        stage('Unit Test Maven'){
            steps{
                script{
                    mvnTest()
                }
            }
        }
    }
}