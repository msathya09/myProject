pipeline {
  agent { label 'linux' }
  tools {
    maven 'maven362'
  }
  stages {
    stage('checkout') {
      steps {
        git credentialsId: 'git_user_cred', url: 'git@github.com:msathya09/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
