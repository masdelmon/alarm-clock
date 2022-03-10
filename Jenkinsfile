  pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
              sh 'mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:3.0:sonar -Dsonar.host.url=http://localhost:9000'
            }
        }  
      }
}
