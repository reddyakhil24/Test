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
    stage('Test PS') {
      steps {
        powershell 'node {     powershell \'Write-Output "Hello, World!"\' }'
      }
      Stage('Test 1') {
        Steps {
        node {
    def msg = powershell(returnStdout: true, script: 'Write-Output "PowerShell is mighty!"')
    println msg
}
        }
      }
    }
  }
}
