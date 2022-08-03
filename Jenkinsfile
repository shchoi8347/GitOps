pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        //  https://github.com/shchoi8347/GitOps will replace by sed command before RUN
        git url: ' https://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@github.com/shchoi8347/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}
