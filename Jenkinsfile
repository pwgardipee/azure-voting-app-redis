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
            sh 'cd azure-vote/'
            sh 'docker build -t jenkins-pipeline .'
            sh 'cd ..'
            
            // sh 'docker build -t jenkins-pipeline .'
            // sh 'docker images -a'
          }
        }
    }
}