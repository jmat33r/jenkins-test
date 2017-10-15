pipeline {
  agent any
  stages {
    stage ('test'){
	steps {      
	sh 'git --version'
        shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
      }
    }
  }
}

