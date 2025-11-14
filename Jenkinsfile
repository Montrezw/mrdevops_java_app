pipeline{

    agent any
    stages{
         
        stage('Git Checkout'){
            steps{
                git branch: 'main', url: 'git@github.com:Montrezw/mrdevops_java_app.git'
            }
        }
    }
}