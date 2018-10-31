pipeline {
  agent any
  stages {
    
    stage('Input') {
            steps {
                input('Do you want to proceed?')
            }
        }
    stage('Wait for user to select choice parameter?') {
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
    stage('wait for user to text input'){
      steps{
        script{
            def userInput = input(id: 'userInput', message: 'Let\'s promote?', parameters: [[$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env']])
            echo ("Env: "+userInput)
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
