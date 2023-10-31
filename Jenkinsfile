pipeline {
	agent any
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/snehal/Documents/Software/apache-maven-3.9.3/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/CICD.war /home/snehal/Documents/Software/apache-tomcat-9.0.76/webapps'
			}}
			stage('Docker build'){
		    steps {
			sh 'docker build -t snehalhub/cicd-pipeline .'
			}}
			stage('Container creation'){
		    steps {
			sh 'docker run -it -d --name=container-pipeline snehalhub/cicd-pipeline /bin/bash'
			}}	
}}
