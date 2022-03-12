  pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
              sh '/home/vagrant/sonar-scanner-4.2.0.1873-linux/bin/sonar-scanner -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd'
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
