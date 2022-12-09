pipeline {
  agent any
  stages {
    stage('Buzz') {
      parallel {
        stage('Buzz') {
          steps {
            echo 'Buzz'
          }
        }

        stage('Bazz') {
          steps {
            sh 'sleep 5'
            sh 'echo "Hi"'
          }
        }

      }
    }

    stage('Buss') {
      steps {
        echo 'Buss'
      }
    }

  }
}