pipeline {
  agent {
    label 'k8s'
  }
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

    stage('confirm') {
      steps {
        input(message: 'Please confirm', id: 'cid', ok: 'Yeah', submitter: 'KKK', submitterParameter: 'QQQ')
      }
    }

    stage('Example') {
      when {
        equals expected: 'Fred', actual: "${PERSON}"
      }
      input {
        message 'Should we continue?'
        id 'Yes, we should.'
        submitter 'alice,bob'
        parameters {
          string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I greet?')
        }
      }
      steps {
        echo "Hello, ${PERSON}, nice to meet you."
      }
    }

  }
  environment {
    BOO = 'BAA'
  }
}