pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
              sh 'mvn clean package   org.sonarsource.scanner.maven:sonar-maven-plugin:3.0:sonar  -Dsonar.host.url=http://localhost:9000'
            }
        }
        stage('Quality Gate') {
            steps {
                  waitForQualityGate() // Reuse taskId previously collected by withSonarQubeEnv
        }
        stage('JaCoCo') {
            steps {
                echo 'Code Coverage'
                jacoco()
            }
        }
      }
}
