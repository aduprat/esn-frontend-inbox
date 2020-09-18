pipeline {

  agent { 
    dockerfile {
      filename 'Dockerfile'
      dir 'test'
    }
  }

  stages {
    stage('Install packages') {
      steps {
        sh 'env'
      }
    }
  }
}
