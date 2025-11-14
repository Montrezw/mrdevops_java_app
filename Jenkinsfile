@Library('my-shared-library') _

pipeline{
    agent any
    stages{
         
        stage('Git Checkout'){
            steps{
                script(
                    gitCheckout(
                        branch: "main"
                        url: "git@github.com:Montrezw/mrdevops_java_app.git"
                    )
                )
            }
        }
    }
}