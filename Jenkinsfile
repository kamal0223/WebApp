pipeline {
  agent any
  stages {
    stage('Dev code pull') {
      steps {
        echo 'this is dev code pull'
      }
    }

    stage('Dev maven build') {
      steps {
        echo 'Dev code build'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'Deploy to QA env'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'All QA tests'
          }
        }

        stage('UI Test') {
          steps {
            echo 'This is UI automation'
          }
        }

        stage('API Test') {
          steps {
            echo 'This is api test'
          }
        }

      }
    }

    stage('QA Certify') {
      steps {
        echo 'QA manual certification'
        input 'can we proceed with the build?'
      }
    }

    stage('UAT deploy') {
      steps {
        echo 'Deploy to UAT env'
      }
    }

    stage('UAT Certification') {
      steps {
        echo 'Manually certify UAT'
        input 'can we proceed with UAT certify?'
      }
    }

    stage('Prod Deployement') {
      steps {
        echo 'Prod deployment'
      }
    }

  }
}