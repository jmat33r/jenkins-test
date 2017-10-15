pipeline {
    agent any
    stages {
        stage ('Build') {
            when {
                expression {
                    return GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    //GIT_BRANCH = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
                    //return GIT_BRANCH == 'origin/master' || params.FORCE_FULL_BUILD
                }
            }
            steps {
                parallel (
                    linux: {
                        build job: 'test_pipeline', parameters: [string(name: 'GIT_BRANCH_NAME', value: GIT_BRANCH)]
                        sh 'printenv'
                    },
                    mac: {
                        build job: 'full-build-mac', parameters: [string(name: 'GIT_BRANCH_NAME', value: GIT_BRANCH)]
                    },
                    windows: {
                        build job: 'full-build-windows', parameters: [string(name: 'GIT_BRANCH_NAME', value: GIT_BRANCH)]
                    },
                    failFast: false)
            }
        }
        stage ('Build Skipped') {
            when {
                expression {
                    GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                    return !(GIT_BRANCH == 'origin/master' || params.FORCE_FULL_BUILD)
                }
            }
            steps {
                echo 'Skipped full build.'
            }
        }
    }
}
