pipeline {
  agent any
    stages {
        stage ('Build') {
            when {
                expression {
                    GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    return GIT_BRANCH
                }
            }
            steps {
               sh 'printenv'
            }
        }
    }
 }

