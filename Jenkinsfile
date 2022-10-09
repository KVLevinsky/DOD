pipeline{
    agent any
    stages{
        stage("Checkout from Git") {
            steps{
                git branch: 'main', credentialsId: 'cred-github', url: 'https://github.com/KVLevinsky/DOD'
            }
        }
        stage("List the files") {
            steps{
                sh 'ls -lahR'
            }
        }
        stage("Build solution") {
            steps{
                sh 'dotnet build .'
            }
        }
        stage("Test solution") {
            steps{
                sh 'dotnet test .'
            }
        }
        stage("Publish solution") {
            steps{
                sh 'dotnet publish .'
            }
        }
        stage("List the files") {
            steps{
                sh 'ls -lahR'
            }
        }
    }
}