pipeline {
    agent {
        label 'wsl'
    }
    stages{
        stage("Primer paso pipeline") {
            steps{
                sh 'echo "saludos desde el terminal"'
            }
        }
        stage("Segundo paso paso pipeline") {
            agent {
                label 'container'
            }            
            steps{
                sh 'node --version'
            }
        }
        stage("Tercer paso paso pipeline") {
            steps{
                sh 'docker ps'
                sh 'security -v unlock-keychain -p "kl154676775" ~/Library/Keychains/login.keychain-db'
            }
        }
        stage("Cuarto paso paso pipeline") {
            agent {
                docker {
                    image 'node:22'
                    label 'wsl'
                }
            }
            steps{
                sh 'node --version'
            }
        }                        
    }
}