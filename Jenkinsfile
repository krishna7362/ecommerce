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
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
     stage('install') {
      steps {
        sh 'mvn insatll'
      }
    }
  }
}
