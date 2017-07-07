pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo "PATH is: $PATH"
        withEnv(['PATH+=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/gradle/bin:/usr/local/ant/bin:/root/bin']) {
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
