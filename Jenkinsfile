
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
   
   post{
   always{
     script{
	    stage_build=currentBuild.currentResult
	    EMAIL_TO="aashishreddy03@gmail.com"
            emailext body: "Hi Team, \n\n Maven build status - ${stage_build} :   \n\n Thanks,\n Ashish",
	    subject: "[ Maven build status ] ", to: "${EMAIL_TO}"
            cleanWs()
	}
       }
    }
}

