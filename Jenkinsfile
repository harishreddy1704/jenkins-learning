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
        sh 'echo building $APP_NAME for $BUILD_ENV'
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
        sh "echo deploying ${APP_NAME} to ${BUILD_ENV}"
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
  
      
