pipeline {
  agent any
  stages {
    stage ('test'){
	steps {      
        GIT_BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
        sh 'echo $GIT_BRANCH'
      }
    }
  }
}

