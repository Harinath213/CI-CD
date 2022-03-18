pipeline{
    agent any

    stages{
        stage("sonar check & analysis"){
            agent {
                docker{
                    image 'openkdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                             sh 'chmod +x gradlew'
                             sh './gradlew sonarqube'
                    
                  }

                }
                
            }
        }
    }
    
}
