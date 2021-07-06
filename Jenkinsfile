pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building a react app '
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the app'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying app on AWS'
      }
    }

  }
}