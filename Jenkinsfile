pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        echo 'Code already checked out by Jenkins SCM step'
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
  
      
