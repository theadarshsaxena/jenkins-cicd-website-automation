pipeline {
  agent any
  stages {
    stage('Testing deployment') {
      parallel {
        stage('Testing deployment') {
          steps {
            sh 'echo "testing is started"'
          }
        }

        stage('Downloading data') {
          steps {
            sh '''cp -v -f * /var/www/html
'''
          }
        }

        stage('Deploying on testing server') {
          steps {
            sh 'echo "testing completed"'
          }
        }

      }
    }

    stage('Deployment to production system') {
      input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                           }
       }
      steps {
        echo "choice: ${params.PERSON}"
        sh 'echo "deployment to production system started"'
      }
    }

  }
}
