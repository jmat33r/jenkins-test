pipeline {
  agent any
    stages {
        stage ('Build') {              
            steps {
                script {
                   GIT_BRANCH_NAME = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                   BRANCH_NAME= sh(returnStdout: true, script: 'git show --quiet --pretty=%d').trim()
                }
                sh """
                    echo more .git/HEAD
                    echo ${GIT_BRANCH_NAME}
                """

                #sh 'printenv'
            }
        }
          stage ('Invoke_pipeline') {
            steps {
                build job: 'tomcat_test1', parameters: [
                string(name: 'param1', value: "value1")
                ]
            }
          }
        
    }
 }

