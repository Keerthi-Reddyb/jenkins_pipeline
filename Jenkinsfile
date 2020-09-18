pipeline {
	agent { label 'slave1' }
 
	stages {
		stage ('STAGE 1') {
			steps {
			    echo 'Building...'
				sh '''
					cd /home/ec2-user/workspace/
					if [ -f central_repo ] ; then
					cd ./central_repo
					git pull
					else
					
					git clone https://github.com/Keerthi-Reddyb/central_repo
					fi
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
					rm -rf Test
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
