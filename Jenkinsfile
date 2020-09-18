pipeline {
	agent { label 'slave1' }
 
	stages {
		stage ('STAGE 1') {
			steps {
			    echo 'Building...'
				sh '''
					cd /home/ec2-user/workspace/c-project-jenkins/
					make
				'''
			}	
		}
		stage ('STAGE 2') {
			steps {
			    echo 'Building...'
				sh '''
				        cd /home/ec2-user/workspace/java-project/
					mvn clean install
					cp *.war /home/ec2-user/apache-tomcat-9.0.38/webapps
				'''	
			}	
		}
		
	}
}
