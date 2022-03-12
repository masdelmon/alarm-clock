  pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
              sh 'mvn clean verify sonar:sonar -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd'
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
