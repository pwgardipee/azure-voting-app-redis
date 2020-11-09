pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
          steps {
            sh 'docker images -a'
            sh """
              cd azure-vote/
              docker build -t jenkins-pipeline .
              cd ..
              docker images -a
            """
          }
        }
        stage('Start Test App') {
          steps {
           sh 'docker compose up'
           sh './scripts/test_container.ps1'
          }

          post {
            success {
              echo 'App Started Successfully'
            }
            failure {
              echo 'App Failed to Start'
            }
          }
        }

        stage('Run Tests') {
          steps {
           sh 'true'
          }
        }

        stage('Stop Test App') {
          steps {
           sh 'docker compose down'
          }
        }
    }
}