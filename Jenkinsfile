pipeline{
    agent any
    stages{
        stages("Checkout from Git") {
            git branch: 'main', credentialsId: 'cred-github', url: 'https://github.com/KVLevinsky/DOD'
        }
    }
}