pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/krishna7362/ecommerce.git', branch: 'master')
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
        bat 'xcopy " C:\\Program Files (x86)\\Jenkins\\workspace\\ecommerce_master\\target\\ecommerce" "C:\\Program Files\\Apache Software Foundation\\Tomcat 8.5\\webapps"'
      }
    }
  }
  post {
    always {
      emailext(body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test')

    }

  }
}