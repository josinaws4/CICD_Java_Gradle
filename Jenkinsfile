pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image "openjdk:11"
                    args '-d'
                }
            }
            steps{
                scripts{
                    withSonarQubeEnv(credentialsId: 'sonar',installationName: 'sonarserver') {
                            sh "chmod +x gradlew"
                            sh "./gradlew sonarqube"
                    }
                }

            }
        }
    }

}
