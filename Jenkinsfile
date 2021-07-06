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
          steps {
            writeFile(file: 'testlog.txt', text: 'automated test')
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
    ChromeDriverPath = '"C:\\Driver-me\\Path\\chromedriver.exe"'
  }
}