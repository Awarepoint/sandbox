pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo "PATH is: $PATH"
        withEnv(['PATH+=/bin']) {
          sh './gradlew clean build'
        }
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
