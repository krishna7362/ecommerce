pipeline {
  agent any
  stages {
    stage('code checkout') {
      steps {
        git 'https://github.com/krishna7362/ecommerce.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn compile'
      }
    }
  }
}