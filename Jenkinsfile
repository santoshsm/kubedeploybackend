pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/santoshsm/kubedeploybackend.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deploy-backend.yaml", kubeconfigId: "clusterk8sconfig")
        }
      }
    }

  }

}
