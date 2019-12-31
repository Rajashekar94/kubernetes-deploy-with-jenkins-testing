node{

  //Checkout Code from Git
  stage('checkout code') {
 git 'https://github.com/Rajashekar94/kubernetes-deploy-with-jenkins-testing.git' 
  }
  
  
  stage('Build image') {
    withCredentials([usernamePassword(credentialsId: 'jenkins_master', passwordVariable: '$admin', usernameVariable: '$admin1')]) 
    // some block


      //Create or update resources
                   sh("kubectl apply -f frontend-deployment.yml")
                                                  
                   sh("kubectl apply -f frontend-svc.yml")

                   sh("kubectl apply -f redis-master-deployment.yml")

                   sh("kubectl apply -f redis-master-svc.yml")

                   sh("kubectl apply -f redis-slave-deployment.yml")

                   sh("kubectl apply -f redis-slave-svc.yml")

}
  }



