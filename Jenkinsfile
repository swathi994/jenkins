
pipeline {
  agent {
    label "docker-agent"
  }
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/swathi994/jenkins.git', branch: 'master'])
       }
    }

  }
}
