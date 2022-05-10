pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent{
                docker{
                    image "openjdk:11"
                }
            }
            steps{
                scripts{
                    withSonarQubeEnv(credentialsId: 'sonar_password') {
                        sh "chmod +x gradlew"
                        sh "./gradlew sonarqube"
                    }
                }

            }
        }
    }

}
