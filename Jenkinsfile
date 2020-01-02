node{

  //Checkout Code from Git
  stage('checkout code') {
 git 'https://github.com/Rajashekar94/kubernetes-deploy-with-jenkins-testing.git' 
  }
  
  
stage('Build image') {
   sshagent(['kubernetes-cluster']) {
    sh "scp -o StrictHostKeyChecking=no frontend-deployment.yml frontend-svc.yml ubuntu@34.68.5.242:/home/ubuntu/guestbook"
        script{
	      try {
		   sh "ssh  ubuntu@34.68.5.242 kubectl apply -f ."
		   }
           sh "ssh  ubuntu@34.68.5.242 kubectl create -f ."  
	       }
  }
}
}


