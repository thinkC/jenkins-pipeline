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
            echo "Get the driverpath ${ChromeDriverPath}"
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
  environment {
    ChromeDriverPath = '"C:\\Driver-me\\Path\\chromedriver.exe"'
  }
}