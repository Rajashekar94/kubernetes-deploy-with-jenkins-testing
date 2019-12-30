node{

  //Checkout Code from Git
stage('checkout code'){  
checkout scm

 stage('Deploy application'){

      /Create or update resources
                   sh("kubectl apply -f frontend-deployment.yml")
                                                  
                   sh("kubectl apply -f frontend-svc.yml")

sh("kubectl apply -f redis-master-deployment.yml")

sh("kubectl apply -f redis-master-svc.yml")

sh("kubectl apply -f redis-slave-deployment.yml")

sh("kubectl apply -f redis-slave-svc.yml")






}


}
