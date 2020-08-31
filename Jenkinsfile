pipeline {
  agent any
  stages {
    stage('GITCheckout') {
      steps {
        echo 'Checking out from GIT'
      }
    }

    stage('Build Stage ') {
      steps {
        echo 'Building the pipeline'
      }
    }

    stage('Testing Stage') {
      parallel {
        stage('Testing Stage') {
          steps {
            echo 'Integration Testing '
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Performance Testing'
          }
        }

      }
    }

    stage('Local Play') {
      steps {
        ansiblePlaybook 'local_play.yml'
        echo 'Invoking local Play'
      }
    }

    stage('Deploy Stage') {
      steps {
        sh '''pwd
echo "Everything is working as expected"'''
      }
    }

  }
}