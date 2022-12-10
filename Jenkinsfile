pipeline {
  agent any
  stages {
    stage('Buzz') {
      parallel {
        stage('BuzzA') {
          steps {
            echo 'Buzz'
            sh 'sleep 5'
          }
        }

        stage('BuzzB') {
          steps {
            sh 'sleep 5'
            sh 'echo "Hi $BOO"'
          }
        }

      }
    }

    stage('Buss') {
      steps {
        echo 'Buss'
        sh 'echo 123 > artifact.txt'
        archiveArtifacts(allowEmptyArchive: true, artifacts: '*.txt', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
  environment {
    BOO = 'BAA'
  }
}