pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Ajayvarma8142/ecommerce.git', branch: 'master')
      }
    }
    stage('build') {
      steps {
        bat 'mvn install'
      }
    }
    stage('sonar') {
      steps {
        bat 'mvn sonar:sonar'
      }
    }
    stage('Email-Notification') {
      steps {
        echo 'Ok'
      }
    }
    stage('Deploy') {
      steps {
        bat 'REM'
      }
    }
  }
  post {
    always {
      emailext(body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test')

    }

  }
}