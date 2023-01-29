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
                sh 'scp -i /var/lib/jenkins/secrets/mykey.pub -r * vagrant@docker01:/var/www/html/'
            }
        }			
		
}
}
