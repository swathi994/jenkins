
pipeline {
  agent {
    label "docker-agent"
  }
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/swathi994/webapp.git', branch: 'master', credentialsId: 'jenkins-user'])
       }
    }
    stage ('Execute tests') {
      steps{
       sh ' sudo systemctl status docker'
      } 
    }
     stage('Deploy to k8s'){
            steps{
                script{
                    kubernetesDeploy (configs: 'deploymentservice.yaml',kubeconfigId: 'k8sconfigpwd')
                    kubernetesDeploy (configs: 'service.yaml',kubeconfigId: 'k8sconfigpwd')
                }
            }
        }
  }
}
