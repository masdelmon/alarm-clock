pipeline {
    
    agent any
    stages {
    stage('SonarQube analysis') {
      steps {
                  withSonarQubeEnv('sq') {
                    sh '''/home/vagrant/sonar-scanner-4.2.0.1873-linux/bin/sonar-scanner \
                    -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd   \
                    -Dsonar.projectKey=com.hello2morrow.sonargraph.test:AlarmClock \
                    -Dsonar.projectName=AlarmClockMain \
                    -Dsonar.projectVersion=1.0 \
                    -Dsonar.sourceEncoding=UTF-8'''
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
