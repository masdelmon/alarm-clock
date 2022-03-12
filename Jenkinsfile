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
                  timeout(time: 1, unit: 'HOURS') { // Just in case something goes wrong, pipeline will be killed after a timeout
                  def qg = waitForQualityGate() // Reuse taskId previously collected by withSonarQubeEnv
                  if (qg.status != 'OK') {
                    error "Pipeline aborted due to quality gate failure: ${qg.status}"
                   }
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
