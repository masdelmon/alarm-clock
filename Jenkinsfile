  pipeline {
    
    agent any
    stages {
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh "mvn clean package   org.sonarsource.scanner.maven:sonar-maven-plugin:3.0:sonar  -Dsonar.host.url=http://localhost:9000"
                }
            }
        }
        stage("Quality gate") {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
        stage('JaCoCo') {
            steps {
                echo 'Code Coverage'
                jacoco()
            }
        }
      }
}
