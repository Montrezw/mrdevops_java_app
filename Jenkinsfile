@Library('my-shared-library')
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