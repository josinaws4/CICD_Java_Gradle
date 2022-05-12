pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image "openjdk:11"
                }
            }
            steps{                
            	withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonarqube') {
                    sh "chmod +x gradlew"
                    sh "./gradlew clean"
                    sh "./gradlew sonarqube  -Dsonar.host.url=http://3.111.32.107:9000  -Dsonar.login=47b1fb11d95101343a2cadbf42da5d947ab965f9 --warning-mode=all"
                }
                
            }
        }
    }
}
