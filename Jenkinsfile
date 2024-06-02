pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube') { 
          sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=opqdemo"
        }
      }
    }
  }
}
