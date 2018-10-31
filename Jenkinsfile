pipeline {
  agent any
  stages {
    
    stage('Input') {
            steps {
                input('Do you want to proceed?')
            }
        }
    stage('Wait for user to input text?') {
    steps {
        script {
             def userInput = input(id: 'userInput', message: 'Merge to?',
             parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
                description:'describing choices', name:'nameChoice', choices: "QA\nUAT\nProduction\nDevelop\nMaster"]
             ])

            println(userInput); //Use this value to branch to different logic if needed
        }
    }

}
    stage('clean workspace') {
      steps {
        cleanWs(cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenAborted: true, cleanWhenUnstable: true, deleteDirs: true, notFailBuild: true, skipWhenFailed: true)
      }
    }
    
  }
}
