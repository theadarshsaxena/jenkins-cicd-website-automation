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
    parameters {
      choice(name: 'CHOICE', choices: ['y', 'n'], description: 'Is It OK')
    }
    stage('Deployment to production system') {
      steps {
        echo "choice: ${params.CHOICE}"
        sh 'echo "deployment to production system started"'
      }
    }

  }
}
