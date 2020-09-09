pipeline {

  agent { 
    dockerfile {
      filename "Dockerfile"
      dir 'test'
    }
  }

  stages {
    stage('Install packages') {
      steps {
        sh 'npm install'
      }
    }

    stage('Run tests') {
      matrix {
        axes {
          axis { 
            name 'BROWSER' 
            values 'Firefox', 'Chrome'
          }
        }

        stages {
          stage('Run tests with') {

            steps {
              sh "npm run test --browser ${BROWSER}"
            }
          }
        }
      }
    }

    stage('Deliver Docker images') {
      when { branch 'main' }
      steps {
        echo "Delivery"
      }
    }

    stage('Deploy new version') {
      when { branch 'main' }
      steps {
        echo "Deploy"
      }
    }
  }
}
