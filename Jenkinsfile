pipeline {
    agent any
	tools {
    maven 'M3'
  }
	
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
          stage ('Build') {
             steps {
                sh '${m2_home}/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/M3/bin/mvn -f java-sample-app/pom.xml clean install' 
            }
	    
        }
    stage ('Deploy') {
             steps {
                sh 'scp  ${WORKSPACE}/java-sample-app/target/java-sample-app-1.0.0.war root@192.168.1.67:/opt/tomcat/webapps'
		 
            }
	    
    
    }
	
}
}