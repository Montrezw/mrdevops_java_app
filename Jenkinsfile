@Library('my-shared-library') _

pipeline{
    agent any
    stages{
         
        stage('Git Checkout'){
            steps{
                script(
                    gitCheckout(
                        branch: "main"
                        url: "https://github.com/Montrezw/JENKINS_SHARED_LIB.git"
                    )
                )
            }
        }
    }
}