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
      parallel {
        stage('Display Time') {
          steps {
            timestamps() {
              echo 'The Time is 4:35 PM'
            }

          }
        }
        stage('EST') {
          steps {
            sh 'TZ=":US/Eastern" date +%Y%m%d'
          }
        }
        stage('US Central') {
          steps {
            sh 'TZ=":US/Central" date +%Y%m%d'
          }
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
        sh '''#!/bin/bash

echo "hello, today is $(date)"'''
      }
    }
  }
}