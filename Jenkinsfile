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

        stage('Test log') {
          environment{
            Localvariable='Hello Local'
          }
          steps {
            writeFile(file: 'testlog.txt', text: 'adding chromedriverpath ${ChromeDriverPath} automated test and local variable value ${Localvariable}')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying app on AWS'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'testlog.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = "C:\\Driver-me\\Path\\chromedriver.exe"
  }
}