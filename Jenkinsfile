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
                sh 'scp -v -o StrictHostKeyChecking=no -r * vagrant@10.10.10.20:/var/www/html/'
            }
        }			
		
}
}
