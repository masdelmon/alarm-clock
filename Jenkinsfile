   pipeline {
    
    agent any
    stages {
        stage('build') {
            steps {
   	       sh 'mvn clean package -Dmaven.test.skip=true com.hello2morrow:sonargraph-maven-plugin:12.0.5:create-report -Dsonargraph.sonargraphBuildVersion=8.7.0 -Dsonargraph.reportFormat=xml -Dsonargraph.prepareForSonarQube=true  -Dsonargraph.installationDirectory=/home/vagrant/SonargraphBuild-12.0.5.717_2022-02-25  -Dsonargraph.licenseFile=/home/vagrant/Sonargraph.license'
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
