pipeline {
    
	agent any
/*	
	tools {
        maven "maven3"
    }
*/		
    stages{
        
        stage('BUILD'){
            steps {
				echo 'Show Os info...'
                sh 'cat /etc/os-release'
            }
        }
		
	stage('Upload Artifacts'){
            steps {
		sh 'sudo systemctl stop nginx.service'
                sh 'scp -i /var/lib/jenkins/secrets/mykey -r * vagrant@docker01:/var/www/html/'
		sh 'sudo systemctl start nginx.service'
            }
        }			
		
}
}
