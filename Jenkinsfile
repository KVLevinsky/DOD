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
                sh 'dotnet publish -c Release .'
            }
        }
        stage("List the files after publishing") {
            steps{
                sh 'ls -lahR'
            }
        }
        stage("Build Docker image") {
            steps{
                sh 'cd WebAppAPI'
                sh 'docker build -t kvlevinsky/sample-webappapi:latest .'
            }
        }
    }
}