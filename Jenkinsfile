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

        stage('Log File') {
          steps {
            writeFile(file: 'TestLog.txt', text: 'Check log file written')
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
      when{
        branch 'main'
      }
      parallel {
        stage('Report') {
          steps {
            input(message: 'Do you want report?', id: 'Ok')
            echo 'Prepare report'
          }
        }

        stage('Archive Artifact') {
          steps {
            archiveArtifacts 'TestLog.txt'
          }
        }

      }
    }

  }
}
