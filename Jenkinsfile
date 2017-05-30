pipeline {
  agent none
  options {
    skipDefaultCheckout()
    }
  stages {
    stage('Checkout') {
        agent any
        steps {
            checkout scm
            stash(name: 'ws', includes: '**') //DON'T DO THIS!
            }
            }
    stage('Build backend') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v $HOME/.m2:/root/.m2'
                }
            }
      steps {
        echo 'Helloes!'
      }
    }
    stage('Test backend') {
      steps {
        echo 'Testing'
      }
    }
    stage('More tests') {
      steps {
        echo 'more testst'
      }
    }
  }
}
