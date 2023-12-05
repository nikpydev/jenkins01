pipeline {
  agent {
    label 'node'
  }
  stages {
    stage('A') {
      parallel {
        stage('A') {
          post {
            always {
              echo '========always========'
            }

            success {
              echo '========A executed successfully========'
            }

            failure {
              echo '========A execution failed========'
            }

          }
          steps {
            echo '========executing A========'
          }
        }

        stage('Build') {
          steps {
            sh '''pwd
date'''
          }
        }

        stage('Test') {
          steps {
            sh 'echo "Parallely run test"'
          }
        }

      }
    }

    stage('B') {
      post {
        always {
          echo '========always========'
        }

        success {
          echo '========B executed successfully========'
        }

        failure {
          echo '========B execution failed========'
        }

      }
      steps {
        echo '========executing B========'
      }
    }

    stage('C') {
      parallel {
        stage('C') {
          steps {
            echo 'This is stage C'
          }
        }

        stage('Sleep') {
          steps {
            sleep 13
          }
        }

      }
    }

  }
  tools {
    nodejs 'NodeJS-01'
  }
  post {
    always {
      echo '========always========'
    }

    success {
      echo '========pipeline executed successfully ========'
    }

    failure {
      echo '========pipeline execution failed========'
    }

  }
}