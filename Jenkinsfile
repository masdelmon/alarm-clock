pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
              sh 'mvn clean package   org.sonarsource.scanner.maven:sonar-maven-plugin:3.0:sonar  -Dsonar.host.url=http://localhost:9000'
            }
        }
        stage('Sonarqube quality gate') {
            steps {
                timeout(time: 10, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
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
