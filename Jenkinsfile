node{

  //Checkout Code from Git
  stage('checkout code') {
 git 'https://github.com/Rajashekar94/kubernetes-deploy-with-jenkins-testing.git' 
  }
  
  
stage('Build image') {
   sshagent(['kubernetes-cluster']) {
    sh "scp -o StrictHostKeyChecking=no frontend-deployment.yml frontend-svc.yml ubuntu@35.238.55.137:/home/ubuntu/guestbook"
        script{
	      try {
		   sh "ssh  ubuntu@35.238.55.137 kubectl apply -f ."
		   } catch(error){
           sh "ssh  ubuntu@35.238.55.137 kubectl create -f ."  
	        }
		   }
}
}
}

