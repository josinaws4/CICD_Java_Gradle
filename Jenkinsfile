pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image "openjdk:11"
                    args '-i --entrypoint='
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
