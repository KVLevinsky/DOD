pipeline{
    agent any
    stages{
        stage("Checkout from Git") {
            steps{
                git branch: 'main', credentialsId: 'cred-github', url: 'https://github.com/KVLevinsky/DOD'
            }
        }
    }
}