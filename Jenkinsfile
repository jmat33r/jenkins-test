pipeline {
  agent any
    stages {
        stage ('Build') {              
            steps {
                script {
                   GIT_BRANCH_NAME = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                }
               sh 'printenv'
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

