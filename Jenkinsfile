  pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
                sh 'mvn clean verify  org.sonarsource.scanner.maven:sonar-maven-plugin:3.0:sonar  -Dsonar.host.url=http://192.168.43.111:9000'
            }
        }  
      }
}
