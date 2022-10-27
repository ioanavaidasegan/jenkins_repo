pipeline {
    parameters {
        string defaultValue: "testValue", name: "testArg"
    }
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
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
        stage ('Cleanup'){
            steps {
                cleanWs()
            }
        }
    }
}
