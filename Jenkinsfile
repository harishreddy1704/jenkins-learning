pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        sh 'git log -1'
      }
    }

    stage('Build') {
      steps {
        sh 'echo "Compiling/Building app here"'
      }
    }

    stage('Test') {
      steps {
        sh 'echo "Running tests here"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "deploying app here"'
      }
    }
  }
}
  
      
