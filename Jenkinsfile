pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'This is my Test'
          }
        }
        stage('Sleep') {
          steps {
            sleep 3
          }
        }
      }
    }
    stage('Display Time') {
      steps {
        timestamps() {
          echo 'The Time is 4:35 PM'
        }

      }
    }
    stage('Pull') {
      steps {
        git(url: 'https://github.com/reddyakhil24/Test', credentialsId: 'reddyakhil24')
      }
    }
    stage('Copy Files in Azure Vm') {
      steps {
        powershell 'Test'
      }
    }
  }
}