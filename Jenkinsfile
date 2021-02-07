pipeline {
  agent any 

  options {
    timestamps()
  }

  stages {
    stage('Code Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      parallel {
        stage ('First Test') {
          steps {
            echo 'Run First Test here...'
          }
        }
        stage('Second Test') {
          steps {
            echo 'Run Second Test here...'
          }
        }
      }
    }
  }

  post {
    failure {
      mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'Jenkins job failure', to: 'practical.jenkins.course@gmail.com'
    }
  }
}
