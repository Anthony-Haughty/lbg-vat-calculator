pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository - trying again
          git branch: 'main', url: 'https://github.com/Anthony-Haughty/lbg-hello-world-maven.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonar-qube-1') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}