pipeline {
  agent any
    stages {
        stage ('Build') {
            environment {
                script {
                    GIT_BRANCH_NAME = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                }
                
            }
            steps {
               sh 'printenv'
            }
        }
    }
 }

