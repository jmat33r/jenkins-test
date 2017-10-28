// Jenkinsfile-When
// ----------------------------------------------------------------------
// This example shows a variety of ways to use 'when' for flow control
// Note: This Jenkinsfile needs to be executed as part of a
//       Multibranch Pipeline project to demonstrate the 'branch' 
//       variable in the stage("BASIC WHEN - Branch") stage
// ----------------------------------------------------------------------
pipeline {
   agent any
    
   environment {
      VALUE_ONE = '1'
      VALUE_TWO = '2'
      VALUE_THREE = '3'
   }
    
   stages {
      stage("Begin") {
         steps {
            echo 'BASIC WHEN - Master Branch!'
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

