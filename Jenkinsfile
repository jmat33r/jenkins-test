pipeline {
  agent any
  stages {
    stage ('test'){
	steps {      
	  script {
            shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
        }
	sh 'echo $shortCommit'
      }
    }
  }
}

