pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred',url: 'https://testraj.azurecr.io') {
                        sh "docker build -t testraj.azurecr.io/shippingservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred',url: 'https://testraj.azurecr.io') {
                        sh "docker push testraj.azurecr.io/shippingservice:latest "
                    }
                }
            }
        }
    }
}
