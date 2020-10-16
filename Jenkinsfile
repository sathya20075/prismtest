pipeline {

  agent {
    kubernetes {
      	cloud 'kubernetes'
      	label 'default'
      	defaultContainer 'jnlp'
      }
    }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/sathya20075/prismtest.git', branch:'master'
      }
    }   
   
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "prism-apimocktest.yml", kubeconfigId: "kubconfig")
        }
      }
    }

  }

}