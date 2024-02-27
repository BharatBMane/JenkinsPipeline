pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build Java application'
          }
        }

        stage('Test') {
          steps {
            echo 'Test application'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy application on server'
      }
    }

    stage('Report') {
      steps {
        echo 'Prepare report'
      }
    }

  }
}