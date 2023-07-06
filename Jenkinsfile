pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from the GitHub repository
                                git branch: 'master', url: 'https://github.com/katvik001/WebDev.git'
            }
        }
        
        stage('Deploy to S3') {
            steps {
                script {
                    def awsCliCommand = "aws s3 sync . s3://vikash.ms365cloud.tech --region 'us-east-1' --delete"
                    sh 'aws --version'

                    // Deploy changes to S3 bucket
                    sh awsCliCommand
                }
            }
        }
        
        stage('Invalidate CloudFront Cache') {
            steps {
                script {
                    def awsCliCommand = "aws cloudfront create-invalidation --distribution-id 'EDKRNH1IKA90H' --paths '/*'"
                    
                    // Invalidate CloudFront cache
                    sh awsCliCommand
                }
            }
        }
    }
}
