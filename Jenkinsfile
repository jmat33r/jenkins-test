pipeline {
  agent any
  stages {
    stage ('test'){
	steps {      
	  script {
            return shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
	    //return GIT_BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
        }
      }
    }
  }
}

