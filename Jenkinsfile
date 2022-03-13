   pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
	       sh 'java -version'
   	       sh 'mvn clean package sonargraph:create-report -Dsonargraph.sonargraphBuildVersion=8.7.0 -Dsonargraph.reportFormat=xml -Dsonargraph.prepareForSonarQube=true -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd'
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
