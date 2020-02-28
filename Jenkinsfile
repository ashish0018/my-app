
node {
   // This is to demo github action	
   stage('SCM Checkout'){
    // Clone repo
	git branch: 'ashish_test', 
	credentialsId: 'ashish0018', 
	url: 'https://github.com/ashish0018/my-app'
   
   }
   
	
   stage('Mvn Package'){
	   // Build using maven
	   
	   sh "mvn clean package "
   }
   
   stage('Email Notification'){
		mail bcc: '', body: """Hi Team, You build successfully deployed
		                       Job URL : ${env.JOB_URL}
							   Job Name: ${env.JOB_NAME}

Thanks,
DevOps Team""", cc: '', from: '', replyTo: '', subject: "${env.JOB_NAME} Success", to: 'aashishreddy03@gmail.com'
   
   }
}

