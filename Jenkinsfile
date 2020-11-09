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
            sh 'cd azure-vote/'

            sh """
              cd azure-vote/
              pwd
              ls
              docker build -t jenkins-pipeline .
              cd ..
            """
            // sh 'docker build -t jenkins-pipeline .'
            // sh 'docker images -a'
          }
        }
    }
}