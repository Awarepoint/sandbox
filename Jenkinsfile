pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo "PATH is: $PATH"
        withEnv(['PATH+=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/gradle/bin:/usr/local/ant/bin:/root/bin']) {
          sh './gradlew clean build'
        }
        archiveArtifacts artifacts: 'build/libs/*'
      }
    }
    stage('user input gate') {
      steps {
        // input 'my message2'
        milestone(1)
        //lock('Deployment')
      }
    }
    stage('last') {
      steps {
        echo 'done!'
      }
    }
  }
}
