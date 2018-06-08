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
    stage('shell') {
      steps {
        sh 'echo $(date)'
      }
    }
    stage('Shell 1') {
      steps {
        sh '''#!/usr/bin/env bash
git clone --depth 1 "$1" temp-linecount-repo &&
  printf "(\'temp-linecount-repo\' will be deleted automatically)\\n\\n\\n" &&
  cloc temp-linecount-repo &&
  rm -rf temp-linecount-repo'''
      }
    }
  }
}