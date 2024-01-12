pipeline {

  agent any

  stages {
    stage('Verify Branch Stage') {
      steps {
        echo "$GIT_BRANCH"
      }
    }
    stage('Docker build'){
        steps {
          pwsh(script: 'docker images -a')
          powershell(script: """
             cd azure-vote/
             docker images -a
             docker build -t jenkins-pipeline .
             docker images -a
             cd..
             """)
        }
      }
    }
   }
    
