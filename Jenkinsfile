pipeline {
  agent any
  stages {
    
    stage('Input') {
            steps {
                input('Do you want to proceed?')
            }
        }
    stage('clean workspace') {
      steps {
        cleanWs(cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenAborted: true, cleanWhenUnstable: true, deleteDirs: true, notFailBuild: true, skipWhenFailed: true)
      }
    }
  }
}
