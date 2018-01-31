pipeline {
  agent any
    stages {
        stage ('Build') {              
            steps {
                sh 'printenv'
            }
        }
          stage ('Invoke_pipeline') {
            steps {
                build job: 'tomcat_test1', wait: false
            }
          }
        
    }
 }

