node{

  //Checkout Code from Git
  stage('checkout code') {
 git 'https://github.com/Rajashekar94/kubernetes-deploy-with-jenkins-testing.git' 
  }
  
  
stage('Build image') {
  //withCredentials([usernamePassword(credentialsId: 'connect', passwordVariable: 'password', usernameVariable: 'username')]) {
    // some block
  //withCredentials([file(credentialsId: 'kubernetesconfig-', variable: 'configfile')]) {
  withCredentials([sshUserPrivateKey(credentialsId: 'kubernetesconfi', keyFileVariable: 'ssh_privatekey', passphraseVariable: 'ssh_password', usernameVariable: 'private_key')]) {

      //Create or update resources
      sh("kubectl apply -f frontend-deployment.yml")
                                                  
                   sh("kubectl apply -f frontend-svc.yml")

                   sh("kubectl apply -f redis-master-deployment.yml")

                   sh("kubectl apply -f redis-master-svc.yml")

                   sh("kubectl apply -f redis-slave-deployment.yml")

                   sh("kubectl apply -f redis-slave-svc.yml")

}
  }
}


