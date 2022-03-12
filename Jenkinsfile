pipeline {
    
    agent any
    stages {
stage('Sonarqube scan') {
            steps {
                    sh '''/home/vagrant/sonar-scanner-4.2.0.1873-linux/bin/sonar-scanner \
                    -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd   \
                    -Dsonar.projectKey=com.hello2morrow.sonargraph.test:AlarmClock \
                    -Dsonar.projectName=AlarmClockMain \
                    -Dsonar.projectVersion=1.0 \
                    -Dsonar.sourceEncoding=UTF-8'''
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
