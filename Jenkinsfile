#!/usr/bin/env groovy
pipeline {
    agent any 
    stages {
	stage ('Upload to AWS') {
	   steps {
		   withAWS(credentials: 'aws-static', region: 'us-east-1'){
			   sh 'echo "Hello In AWS"'
s3Upload acl: 'Public', 'udacity-project3-s3-bucket', file: 'index.html'
		           }
		  }
	     }		
       }
}
