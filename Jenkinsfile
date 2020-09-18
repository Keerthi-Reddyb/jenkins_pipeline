pipeline {
	agent { label 'slave1' }
 
	stages {
		stage ('STAGE 1') {
			steps {
			    echo 'Building...'
				sh '''
					cd /home/ec2-user/workspace/
					rm -rf central_repo
					git clone https://github.com/Keerthi-Reddyb/central_repo
					cd /home/ec2-user/workspace/central_repo/
					make
				'''
			}	
		}
		stage ('STAGE 2') {
			steps {
			    echo 'Building...'
				sh '''
				        cd /home/ec2-user/workspace/
					rm -rf java-project3 Test
					git clone https://github.com/Keerthi-Reddyb/Test
				        cd /home/ec2-user/workspace/Test/webapp/
					mvn clean install
					cd /home/ec2-user/workspace/Test/webapp/target
					cp *.war /home/ec2-user/apache-tomcat-9.0.38/webapps
				'''	
			}	
		}
		
	}
}
