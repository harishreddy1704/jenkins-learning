pipeline {
  agent any

  environment {
    APP_NAME = 'jenkins-learning-app'
    BUILD_ENV = 'staging'
  }

  stages {
    stage('Checkout') {
      steps {
        sh 'git log -1'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t jenkins-learning-app:latest'
        
      }
    }

    stage('Quality checks') {
      parallel {
        stage('Lint') {
          steps {
            sh 'echo "running linter"'
          }
        }
        stage('Unit Test') {
          steps {
            sh 'echo "running unit test"'
          }
        }
      }
    }

    stage('Test') {
      steps {
        sh 'echo "Running tests here"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker run --rm jenkins-learning-app:latest'
      }
    }
  }

  post {
    success {
      echo "Pipeline succeeded for ${APP_NAME}!"
    }
    failure {
      echo "Pipeline failed -- check logs above"
    }
    always {
      echo "Pipeline finished. Cleaning up if needed"
    }
  }  
}
  
      
