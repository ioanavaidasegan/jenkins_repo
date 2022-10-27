pipeline {
  agent any
  stages {
    stage('Hello') {
      parallel {
        stage('Hello') {
          steps {
            echo 'Hello World'
          }
        }

        stage('Stage2') {
          steps {
            echo 'Stage 2 message'
          }
        }

      }
    }

    stage('Execute shell') {
      agent {
        label 'built-in'
      }
      steps {
        sh 'ls'
        sh 'chmod +x hello.sh'
        sh './hello.sh'
      }
    }

    stage('Cleanup') {
      steps {
        cleanWs()
      }
    }

  }
  parameters {
    string(defaultValue: 'testValue', name: 'testArg')
  }
}