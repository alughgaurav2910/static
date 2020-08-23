#!/usr/bin/env groovy
pipeline {
    agent any 
    stages {
	stage ('Lint HTML') {
		step {	tidy -q -e *.html
	              }	
		}
	stage ('Upload to AWS') {
	   steps {
		   withAWS(credentials: 'aws-static', region: 'us-east-1'){
			   sh 'echo "Hello In AWS"'
                   s3Upload (bucket: 'udacity-project3-s3-bucket', file: 'index.html')
		           }
		  }
	     }		
       }
}
