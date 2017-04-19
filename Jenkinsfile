pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh './gradlew clean build'
      }
    }
    stage('user input gate') {
      steps {
        parallel(
          "user input gate": {
            input 'my message'
            
          },
          "intermediate step": {
            echo 'intermediate'
            
          }
        )
      }
    }
    stage('last') {
      steps {
        echo 'done!'
      }
    }
  }
}