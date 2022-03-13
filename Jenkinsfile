   pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
	       sh 'java -version'
   	       sh 'mvn clean package -Dmaven.test.skip=true com.hello2morrow:sonargraph-maven-plugin:12.0.5:create-report -Dsonargraph.sonargraphBuildVersion=8.7.0 -Dsonargraph.reportFormat=xml -Dsonargraph.prepareForSonarQube=true -Dsonar.login=1fc93d0ff8d916343f84972a86a46d5da73fd3cd'
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
