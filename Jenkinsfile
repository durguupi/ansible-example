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
        sleep 20
        echo 'Tested the Sleep condition'
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

    stage('Docker Install ') {
      steps {
        ansiblePlaybook(colorized: true, playbook: 'dockerinstall_play.yml', become: true)
      }
    }

    stage('Deploy Stage') {
      steps {
        sh '''docker --version
<<<<<<< HEAD
            newgrp docker
            docker ps
            echo "Docker is installed Successfully" '''
=======
newgrp docker
docker ps
echo "Docker is installed Successfully" '''
>>>>>>> 97a446c9c3a33e12a6e287e95817d29ec88d98b1
      }
    }

  }
}