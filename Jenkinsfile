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

	stage('UNIT TEST'){
            steps {
                sh 'mvn test'
            }
        }

	stage('INTEGRATION TEST'){
            steps {
                sh 'mvn verify -DskipUnitTests'
            }
        }
		
	stage('Upload Artifacts'){
            steps {
                sh '‘scp -r * vagrant@10.10.10.20:/var/www/html/’'
            }
        }			
		
}
}
